<template>
  <div>
    <Header v-if="name === 'Header'" />
    <Input v-else-if="name === 'Input'" />
  </div>
</template>

<script>
import Header from "./Options/Header.vue";
import Input from "./Options/Input.vue";

export default {
  name: "Options",
  components: {
    Header,
    Input
  },
  props: {
    name: {
      type: String,
      required: true
    },
  }
}
</script>

<style scoped>

</style>