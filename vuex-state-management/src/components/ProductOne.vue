<template>
  <div>
    <h2>productOne</h2>
    <ul>
      <li v-for="product in saleProducts" :key="product">
        <span class="name">{{ product.name }}</span>
        <span class="price"> ${{ product.price }}</span>
      </li>
    </ul>
    <button @click="reducePrice(4)">reduce Price</button>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import { mapGetters } from "vuex";
import { mapState } from "vuex";
export default {
  name: "ProductTwo",
  computed: {
    ...mapState(["products"]),

    // products() {
    //   return this.$store.state.products;
    // },

    // saleProduts(){
    //   return this.$store.getters.saleProducts
    // }

    ...mapGetters(["saleProducts"]),
  },
  methods: {
    // reducePrice(amount){
    //   // this.$store.state.products.forEach((product) => {
    //   //   product.price -= 1
    //   // })
    //   // this.$store.commit('reducePrice')

    //   this.$store.dispatch('reducePrice',amount)

    // }
    ...mapActions(["reducePrice"]),
  },
};
</script>

<style scoped>
div {
  background: #fff8b1;
  box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 30px;
  padding: 10px 20px;
}
ul {
  padding: 0;
}
li {
  display: inline-block;
  margin-right: 10px;
  margin-top: 10px;
  padding: 20px;
  background: rgba(255, 255, 255, 0.7);
}
.price {
  font-weight: bold;
  color: #e8800c;
}
</style>
