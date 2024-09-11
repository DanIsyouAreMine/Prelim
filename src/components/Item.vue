<template>
  <div>
    <p>{{ item.name }} - ${{ item.price }}</p>
    <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addToCart() {
      this.$emit('add-to-cart', this.item);
    },
  },
};
</script>

<style scoped>
</style>
