<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-4">
        <div class="menu">
          <div class="menu__title">
            Form Elements
          </div>
          <draggable
              class="dragArea list-group"
              :list="list1"
              :group="{ name: 'people', pull: 'clone', put: false }"
              :clone="cloneDog"
              @change="log"
          >
            <div class="menu__item" v-for="element in list1" :key="element.id">
              {{ element.name }}
            </div>
          </draggable>
        </div>
      </div>
      <div class="col-8">
        <div class="form">
          <draggable
              class="dragArea list-group"
              :list="list2"
              group="people"
              @change="log"
          >
            <div class="form__item" v-for="element in list2" :key="element.id">
              {{ element.name }}
            </div>
          </draggable>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";
let idGlobal = 8;
export default {
  name: 'Home',
  display: "Custom Clone",
  order: 3,
  components: {
    draggable
  },

  data() {
    return {
      list1: [
        { name: "Input", id: 1 },
        { name: "select", id: 2 },
        { name: "textarea", id: 3 },
        { name: "checkbox", id: 4 }
      ],
      list2: [
        { name: "Header", id: 5 },
      ]
    }
  },
  methods: {
    log: function(evt) {
      window.console.log(evt);
    },
    cloneDog({ id }) {
      if (id === 1) {
        return {
          id: idGlobal++,
          name: "Input1"
        };
      } else if (id === 2) {
        return {
          id: idGlobal++,
          name: "select2"
        };
      } else if (id === 3) {
        return {
          id: idGlobal++,
          name: "textarea3"
        };
      } else if (id === 4) {
        return {
          id: idGlobal++,
          name: "checkbox4"
        };
      }
    }
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
  &__item {
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
    &:last-child {
      border-bottom: none;
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

  &__item {
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
    &:last-child {
      border-bottom: none;
    }
  }
}
</style>