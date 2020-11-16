<template>
  <div class="v-main-wrapper">
    <v-catalog />
    <v-cart v-if="CART.length" :cart_data="CART" />
  </div>
</template>

<script>
import vCatalog from "@/components/v-catalog";
import vCart from "@/components/v-cart";
import { mapGetters } from "vuex";
export default {
  name: "v-main-wrapper",
  components: {
    vCatalog,
    vCart,
  },
  props: {},
  data() {
    return {
      title: "onliner",
    };
  },
  computed: {
    ...mapGetters(["CART"]),
  },
  methods: {},
  watch: {},
  mounted() {},
};
</script>

<style>
.v-main-wrapper {
  max-width: 900px;
  margin: 0 auto;
}
</style>