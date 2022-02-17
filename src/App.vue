<template>
  <div id="app">
    <Test />
  </div>
</template>

<script>
import vCarousel from "./components/v-carousel.vue";
import Test from "./views/Test.vue";
export default {
  name: "App",
  components: {
    Test,
    vCarousel,
  },
};
</script>

<style lang="scss">
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
