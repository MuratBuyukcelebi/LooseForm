<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-4">
        <div class="menu">
          <div class="menu__title">
            Form Elements
          </div>
          <draggable
              class="dragArea list-group menu__list"
              :list="list1"
              :clone="cloneDog"
              @change="log"
              :group="{ name: 'people', pull: 'clone', put: false }"
              :move="onMove"
          >
            <div class="menu__list-item" v-for="element in list1" :key="element.id">
              {{ element.name }}
            </div>
          </draggable>
        </div>
      </div>
      <div class="col-8">
        <div class="form position-relative">
          <div class="d-flex justify-content-center align-items-center fs-3" v-if="list2.length === 0">
            PUT IN
          </div>
          <draggable
              class="dragArea list-group w-100 py-4 form__list"
              :list="list2"
              @change="log"
              group="people"
          >
            <div v-for="element in list2" :key="element.id">
              <Options :id="element.id" />
            </div>
          </draggable>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";
import Options from "../components/Form/Options.vue";

const message = [
  "Header",
  "Input",
  "textarea",
  "checkbox",
  "header"
];

let idGlobal = 0;
export default {
  name: 'Home',
  components: {
    draggable,
    Options
  },

  data() {
    return {
      list1: message.map((name) => {
        return { name, fixed: true, id: idGlobal++ };
      }),
      list2: []
    }
  },
  methods: {
    log: function(evt) {
      window.console.log(evt);
    },
    cloneDog({ id }) {
      if (id === 0) {
        return {
          id: 0,
        };
      } else if (id === 1) {
        return {
          id: 1,
        };
      } else if (id === 2) {
        return {
          id: 2,
        };
      } else if (id === 3) {
        return {
          id: 3,
        };
      } else if (id === 4) {
        return {
          id: 4,
        };
      }
    },
    onMove({ relatedContext }) {
      const relatedElement = relatedContext.element;
      return (
          (!relatedElement || !relatedElement.fixed)
      );
    },
  }
}
</script>
<style scoped lang="scss">
.menu {
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
.form {
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
</style>