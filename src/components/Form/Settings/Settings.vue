<template>
  <div class="settings" :class="{ active : active === true}">
    <div class="settings-item">
      <!--Tittle-->
      <div class="settings-item__title">Title Size</div>
      <div class="settings-item__actions">
        <button @click="$emit('size', 'md')">Default</button>
        <button @click="$emit('size', 'lg')">Large</button>
        <button @click="$emit('size', 'sm')">Small</button>
      </div>
      <div class="settings-item__description">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Settings",

  props: {
    active: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped lang="scss">
.settings {
  position: absolute;
  top: 48px;
  border-radius: 8px;
  right: 0;
  transition: all 0.2s;
  height: 100%;
  overflow: hidden;
  transform: translateX(100%);
  border: 2px solid #42b883;
  padding: 48px 24px;
  max-width: 280px;

  &-item {
    border-top: 1px solid #42b883;
    border-bottom: 1px solid #42b883;
    padding: 16px 0;

    &__title {
      font-size: 24px;
      font-weight: bold;
      color: #fff;
      margin-bottom: 8px;
    }
    &__actions {
      display: flex;
      margin-bottom: 16px;
      gap: 4px;

      button {
        border: 2px solid #42b883;
        border-radius: 8px;
        padding: 6px;
        font-size: 16px;
        font-weight: bold;
        color: #fff;
        background-color: #0F0F0F;
        cursor: pointer;
        transition: all 0.2s ease-in-out;

        &:hover {
          background-color: #42b883;
          color: #0F0F0F;
        }
      }
    }
    &__description {
      font-size: 14px;
      color: #fff;
      opacity: 0.7;
    }
  }

  &.active {
    transform: translateX(0);
  }
}
</style>