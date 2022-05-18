<template>
<div class="settings">
  <slot />
  <div class="settings__actions">
    <button>close</button>
    <button>Setting</button>
  </div>
</div>
</template>

<script>
export default {
  name: "ItemSettings",
}
</script>

<style scoped lang="scss">
.settings {
  transition: all 0.2s;
  position: relative;
  display: flex;
  align-items: center;

  &__actions {
    position: absolute;
    right: 8px;
    display: flex;
    justify-content: flex-end;
    flex-direction: column;
    opacity: 0;
    margin-top: auto;
    transition: all 0.2s;
  }

  &:hover {
    padding: 8px;
    border: 1px solid #ccc;
  }
  &:hover & {
    &__actions {
      opacity: 1;
    }
  }
}
</style>