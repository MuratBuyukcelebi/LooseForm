<template>
<div class="menu">
  <div class="menu__title">
    Form Elements
  </div>
  <draggable
      class="dragArea list-group menu__list"
      :list="list1"
      :group="{ name: 'people', pull: 'clone', put: false }"
      :clone="cloneDog"
      @change="log"
  >
    <div class="list-group-item menu__list-item" v-for="element in list1" :key="element.id">
      {{ element.name }}
    </div>
  </draggable>
</div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "Menu",
  components: {
    draggable
  },

  data() {
    return {
      list1: [
        { name: "dog 1", id: 1 },
        { name: "dog 2", id: 2 },
        { name: "dog 3", id: 3 },
        { name: "dog 4", id: 4 }
      ],
      list2: [
        { name: "cat 5", id: 5 },
        { name: "cat 6", id: 6 },
        { name: "cat 7", id: 7 }
      ]
    }
  },
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
    overflow-y: auto;
    max-height: 500px;

    &-item {
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
}
</style>