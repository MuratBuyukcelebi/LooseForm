<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-4"><Menu /></div>
      <div class="col-8"><Form /></div>
    </div>
  </div>
</template>

<script>
import Menu from "@/components/Home/Menu";
import Form from "@/components/Home/Form";

export default {
  name: 'Home',
  components: {
    Form,
    Menu
  },
}
</script>
