<template>
  <div class="settings">
    <!--TEXT-->
    <div class="settings__title">Text Settings</div>
    <input type="range" min="12" max="48" value="14" class="settings__range" @change="range">
    <span id="rangeNumber">14</span>
  </div>
</template>

<script>
export default {
  name: "Settings",

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
  right: 0;
  height: 100%;
  border: 2px solid #42b883;
  border-radius: 8px;
  padding: 24px;

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
    background: #fff;
    outline: none;
    opacity: 0.7;
    -webkit-transition: .2s;
    transition: opacity .2s;
    border-radius: 8px;

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
      border-radius: 50%;
    }

    &::-moz-range-thumb {
      border-radius: 50%;
      width: 20px;
      height: 20px;
      background: #42b883;
      cursor: pointer;
    }
  }
}
</style>