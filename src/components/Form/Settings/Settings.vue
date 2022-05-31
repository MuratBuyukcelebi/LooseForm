<template>
  <div class="settings" :class="{ active : active === true}">
    <div class="settings-item">
      <!--Tittle-->
      <div class="settings-item__title">Başlık Boyutu</div>
      <div class="settings-item__actions">
        <button @click="$emit('size', 'md')">Default</button>
        <button @click="$emit('size', 'lg')">Large</button>
        <button @click="$emit('size', 'sm')">Small</button>
      </div>
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
  methods: {
    range(e) {
      this.e = e.target.value;
      document.getElementById("rangeNumber").innerHTML = this.e;
    }
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
  white-space: nowrap;
  transform: translateX(100%);
  border: 2px solid #42b883;
  padding: 48px 24px;

  &-item {
    &__title {
      font-size: 24px;
      font-weight: bold;
      color: #fff;
      margin-bottom: 8px;
    }
  }

  &.active {
    transform: translateX(0);
  }
}
</style>