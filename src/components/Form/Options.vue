<template>
  <div>
    <Header :size="size" v-if="name === 'Header'" />
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
    size: {
      type: String,
      default: "md",
      validator(value) {
        return ["sm", "md", "lg"].includes(value);
      }
    }
  }
}
</script>