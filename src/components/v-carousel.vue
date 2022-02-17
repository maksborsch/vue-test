<template>
  <div class="wrapper">
    <div
      class="v-carousel"
      :style="{ 'margin-left': '-' + 100 * currentItemIndex + '%' }"
    >
      <v-carousel-item
        v-for="item in carousel_data"
        :key="item.id"
        :item_data="item"
      />
    </div>
    <button @click="prevItem">Prev</button>
    <button @click="nextItem">Next</button>
  </div>
</template>

<script>
import Vue from "vue";
import VueSwal from "vue-swal";
import vCarouselItem from "./v-carousel-item";
Vue.use(VueSwal);
export default {
  name: "v-carousel",
  components: {
    vCarouselItem,
  },
  props: {
    carousel_data: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      currentItemIndex: 0,
    };
  },
  methods: {
    prevItem() {
      if (this.currentItemIndex > 0) {
        this.currentItemIndex--;
      }
    },
    nextItem() {
      if (this.currentItemIndex >= this.carousel_data.length - 1) {
        this.$swal("It's last element");
        this.currentItemIndex = 0;
      } else {
        this.currentItemIndex++;
      }
    },
  },
};
</script>

<style lang="scss">
.wrapper {
  max-width: 600px;
  overflow: hidden;
  margin: 0 auto;
}
.v-carousel {
  display: block;

  display: flex;
}
button {
  margin: 10px;
}
</style>
