<template>
  <div>
    <h1>TEST. Max Borshchevskyi</h1>
    <v-carousel :carousel_data="list" />
  </div>
</template>

<script>
import vCarousel from "../components/v-carousel.vue";
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";
Vue.use(VueAxios, axios);
export default {
  name: "Test",
  components: {
    vCarousel,
  },
  data() {
    return {
      list: undefined,
    };
  },
  mounted() {
    Vue.axios
      .get("https://jsonplaceholder.typicode.com/posts/1/comments")
      .then((response) => {
        this.list = response.data;
        console.warn(response.data);
      });
  },
};
</script>
