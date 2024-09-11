<template>
  <div>
    <h1>Item List</h1>
    <ul>
      <li v-for="item in filteredItems" :key="item.id">
        <Item :item="item" @add-to-cart="handleAddToCart" />
      </li>
    </ul>
  </div>
</template>

<script>
import Item from './Item.vue';

export default {
  components: {
    Item,
  },
  data() {
    return {
      items: [
        { id: 1, name: 'Apple', price: 1.00, isVisible: true },
        { id: 2, name: 'Banana', price: 0.75, isVisible: false },
        { id: 3, name: 'Cherry', price: 2.00, isVisible: true },
      ],
    };
  },
  computed: {
    filteredItems() {
      return this.items.filter(item => item.isVisible);
    },
  },
  methods: {
    handleAddToCart(item) {
      console.log(`Added to cart: ${item.name} - $${item.price}`);
    },
  },
};
</script>

<style scoped>
</style>
