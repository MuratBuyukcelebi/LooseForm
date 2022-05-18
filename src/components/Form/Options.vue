<template>
  <div class="">
    <Header v-if="id === 0" />
    <Input v-else-if="id === 1">31</Input>
    <div v-else-if="id === 2">22</div>
    <div v-else-if="id === 3">31</div>
    <div v-else-if="id === 4">222</div>
    <div v-else-if="id === 5">2233</div>
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
    id: {
      type: Number,
      required: true
    }
  }
}
</script>

<style scoped>

</style>