<template>
  <div class="header">
    <a href="#" class="header__logo">
      <img src="../../assets/logo.png" alt="Logo"/>
      <span class="header__logo-title">LooseForm</span>
    </a>
    <button class="header__button">Start</button>
  </div>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 36px;
  background-color: #0F0F0F;
  border-bottom: 2px solid #42b883;

  &__logo {
    display: flex;
    align-items: center;
    gap: 8px;
    text-decoration: none;

    &-title {
      font-size: 20px;
      font-weight: bold;
      color: #fff;
    }

    img {
      width: 36px;
      height: 36px;
    }
  }
  &__button {
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
    border:2px solid #42b883;
    background-color: transparent;
    padding: 6px 36px;
    color: #fff;
    font-size: 20px;
    font-weight: bold;
    transition: all 0.2s;

    &:hover {
      background-color: #42b883;
      color: #1F1F1F;
    }
  }
}
</style>