<template>
  <div class="settings">
    <!--TEXT-->
    <div class="settings__title">Text Settings</div>
    <input type="range" min="1" max="100" value="50" class="slider" id="myRange">
  </div>
</template>

<script>
export default {
  name: "Settings"
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
}
</style>