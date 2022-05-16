<template>
<div class="menu">
  <div class="menu__title">
    Form Elements
  </div>
  <div class="menu__list">
    <div class="menu__list-item" v-for="(item, key) in list" :key="key">
      {{ item.element }}
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "Menu",

  data() {
    return {
      list: [
        {
          element: "Input",
        },
        {
          element: "Select",
        },
        {
          element: "user",
        },
        {
          element: "email",
        },
        {
          element: "Input",
        },
        {
          element: "Select",
        },
        {
          element: "user",
        },
        {
          element: "email",
        },
        {
          element: "Input",
        },
        {
          element: "Select",
        },
        {
          element: "user",
        },
        {
          element: "email",
        },
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