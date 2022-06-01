<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<style lang="scss">
::-webkit-scrollbar {
  width: 12px;
}
::-webkit-scrollbar-track {
  background: rgba(#2c3e50, 0.5);
}
::-webkit-scrollbar-thumb {
  background: rgba(#42b883, 1);
}
body {
  background-color: #0F0F0F !important;
  overflow-x: clip;
  word-break: break-word;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #fff;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #00EEC9;
    }
  }
}
</style>
<script>
import Header from "@/components/Layout/Header";

export default {
  components: {
    Header
  }
}
</script>