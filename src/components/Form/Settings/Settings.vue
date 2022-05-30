<template>
  <div class="settings" :class="{ active : active === true}">
    <!--TEXT-->
    <div class="settings__title">{{ option.name + option.id }}</div>
    <input type="range" min="12" max="48" value="14" class="settings__range" @change="range">
    <span id="rangeNumber">14</span>
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
    option: {
      type: Object,

      name: {
        type: String,
      },
      id: {
        type: String,
      },
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
  padding-top: 48px;
  padding-bottom: 48px;
  overflow: hidden;
  width: 0;
  opacity: 0;

  &__title {
    font-size: 24px;
    font-weight: bold;
    color: #fff;
    margin-bottom: 8px;
  }
  &__range {
    -webkit-appearance: none;
    width: 100%;
    height: 16px;
    background: #1F1F1F;
    outline: none;
    opacity: 0.7;
    -webkit-transition: .2s;
    transition: opacity .2s;
    border-radius: 6px;

    &:hover {
      opacity: 1;
    }

    &::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 20px;
      height: 20px;
      background: #42b883;
      cursor: pointer;
      border-radius: 6px;
    }

    &::-moz-range-thumb {
      border-radius: 6px;
      width: 20px;
      height: 20px;
      background: #42b883;
      cursor: pointer;
    }
  }

  &.active {
    opacity: 1;
    width: 260px;
    border: 2px solid #42b883;
    padding: 24px;
  }
}
</style>