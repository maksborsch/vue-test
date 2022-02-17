<template>
  <div class="v-carousel-item">
    Name: {{ item_data.name }} <br />
    Email: {{ item_data.email }}
  </div>
</template>

<script>
export default {
  name: "v-carousel-item",
  props: {
    item_data: {
      type: Object,
      default: () => {},
    },
  },
};
</script>
<style lang="scss">
.v-carousel-item {
  min-width: 600px;
  text-align: center;
  display: block;
}
</style>
