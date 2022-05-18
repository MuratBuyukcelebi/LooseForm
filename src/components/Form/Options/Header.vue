<template>
  <div class="header">
    <div class="text-muted fs-6 fw-bold" contentEditable="true">top</div>
    <div class="fs-1 fw-bold" contentEditable="true">Header</div>
    <div class="fs-5 text-muted fw-lighter" contentEditable="true">description</div>
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
  flex-direction: column;
}
</style>