<template>
  <div class="v-cart-item">
    <img class="v-cart-item__image" :src="cart_item_data.url" alt="" />
    <div class="v-cart-item__info">
      <h3>{{ cart_item_data.title }}</h3>
      <p>Price: {{ cart_item_data.title }} eura</p>
    </div>
    <div class="v-cart-item__quantity">
      <span>Quantity: </span>
      {{ cart_item_data.quantity }}
    </div>
    <button @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
export default {
  name: "v-cart-item",
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  methods: {
    deleteFromCart() {
      this.$emit("deleteFromCart");
    },
  },
  mounted() {
    this.$set(this.cart_item_data, "quantity", 1);
  },
};
</script>

<style lang="scss">
.v-cart-item {
  display: flex;
  justify-content: space-between;
  flex-wrap: nowrap;
  align-items: center;
  margin-bottom: 20px;
  border: 1px solid #eee;
  background: #f9f9f9;
  padding: 10px;
  &__image {
    width: 70px;
  }
}
</style>