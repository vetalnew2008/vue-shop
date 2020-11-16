<template>
  <div class="v-catalog-item">
    <img class="v-catalog-item__image" :src="product_data.url" alt="" />
    <h3 class="v-catalog-item__name">{{ product_data.title }}</h3>
    <p class="v-catalog-item__price">Price: {{ product_data.title }} eura</p>
    <button class="v-catalog-item__add_to_cart_btn btn" @click="addToCart">
      add to cart
    </button>
  </div>
</template>

<script>
export default {
  name: "v-catalog-item",
  components: {},
  props: {
    product_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {
      title: "onliner",
    };
  },
  methods: {
    addToCart() {
      this.$emit("addToCart", this.product_data);
    },
  },
};
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  box-shadow: 0 0 10px #999;
  padding: $padding * 2;
  margin-bottom: $margin * 2;
  &__image {
    width: 100px;
  }
}
</style>