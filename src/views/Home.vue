<template>
  <div class="home">
    <div class="container">
      <div class="row">
        <div class="col-4">
          <div class="home-menu">
            <div class="home-menu__title">
              Form Elements
            </div>
            <draggable
                class="dragArea list-group home-menu__list"
                :list="list1"
                :clone="cloneDog"
                @change="log"
                :group="{ name: 'people', pull: 'clone', put: false }"
                :move="onMove"
            >
              <div class="home-menu__list-item" v-for="element in list1" :key="element.id">
                {{ element.name }}
              </div>
            </draggable>
          </div>
        </div>
        <div class="col-8">
          <div class="home-form position-relative">
            <div class="d-flex justify-content-center align-items-center fs-3" v-if="list2.length === 0">
              PUT IN
            </div>
            <draggable
                class="dragArea list-group w-100 py-4 home-form__list"
                :list="list2"
                @change="log"
                group="people"
            >
              <ItemSettings
                  :key="element.id" v-for="(element, index) in list2"
                  @remove="remove(index)"
                  @option="option(element.name, element.id)"
              >
                <component :is="element.name" :size="element.size"/>
              </ItemSettings>
            </draggable>
          </div>
        </div>
      </div>
      <Settings :active="settingsOpen" :selected-option="settingsName" @size="size" >
        {{ settingsId }}
      </Settings>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";
import ItemSettings from "../components/Form/Settings/ItemSettings.vue";
import Settings from "@/components/Form/Settings/Settings";
import Header from "@/components/Form/Options/Header";
import Input from "@/components/Form/Options/Input.vue";

const message = [
  "Header",
  "Input",
  "textarea",
  "checkbox",
];

let idGlobal = 0;
export default {
  name: 'Home',
  components: {
    Settings,
    draggable,
    ItemSettings,
    Input,
    Header,
  },

  data() {
    return {
      list1: message.map((name) => {
        return { name, fixed: true, id: idGlobal++ };
      }),
      list2: [
        {
          name: "Header",
          id: idGlobal++,
          size: "lg",
        },
        {
          name: "Input",
          id: idGlobal++,
          size: "md",
        },
      ],
      settingsOpen: false,
      settingsId: "",
      settingsName: "",
    }
  },
  methods: {
    log: function(evt) {
      window.console.log(evt);
    },
    remove(index) {
      this.settingsOpen = false;
      this.$delete(this.list2, index);
    },
    option(name, id) {
      this.settingsId = id;
      this.settingsName = name;
      this.$forceUpdate();
      console.log(id);
      this.settingsOpen = !this.settingsOpen;
    },
    cloneDog({ id }) {
      if (id === 0) {
        return {
          name: "Header",
          id: idGlobal++,
          size: 'md',
        };
      } else if (id === 1) {
        return {
          name: "Input",
          id: idGlobal++,
          size: 'md',
        };
      } else if (id === 2) {
        return {
          name: "Header",
          id: idGlobal++,
          size: 'md',
        };
      } else if (id === 3) {
        return {
          name: "Header",
          id: idGlobal++,
          size: 'md',
        };
      }
    },
    onMove({ relatedContext }) {
      const relatedElement = relatedContext.element;
      return ((!relatedElement || !relatedElement.fixed));
    },
    size(size) {
      this.list2.forEach((element) => {
        if (element.id === this.settingsId) {
          element.size = size;
          console.log( "SettingsID: " + this.settingsId + " | " + "ItemID: " + element.id + " | " +  "size: " + element.size);
        }
        return element;
      });
    },
  }
}
</script>
<style scoped lang="scss">
.home {
  padding: 48px 0;
  position: relative;

  &-menu {
    display: flex;
    flex-direction: column;
    padding-top: 24px;
    background-color: #0F0F0F;
    border: 2px solid #42b883;
    border-radius: 8px;
    overflow: hidden;
    height: 100%;

    &__title {
      font-size: 24px;
      font-weight: bold;
      text-align: center;
      padding-bottom: 24px;
      border-bottom: 2px solid #42b883;
    }
    &__list {
      display: flex;
      flex-direction: column;
      padding-bottom: 16px;
      overflow-y: auto;
      height: 500px;

      &-item {
        position: relative;
        display: block;
        border-bottom: 1px solid #42b883;
        padding: 16px;
        transition: all 0.2s ease-in-out;
        font-size: 16px;
        text-transform: uppercase;
        cursor: pointer;

        &:hover {
          background-color: #1F1F1F;
        }
      }
    }
  }
  &-form {
    display: flex;
    flex-direction: column;
    padding: 36px;
    background-color: #0F0F0F;
    border: 2px solid #42b883;
    border-radius: 8px;

    &__list {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
  }
}
</style>