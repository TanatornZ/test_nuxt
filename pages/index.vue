<template>
  <div class="container min-auto">
    <h2 class="m-2 text-xl">รายการสินค้า</h2>
    <shop :count="productId.length" class="absolute right-6 bottom-20" />
    <center>
    <button @click="Gotoprice()" class="p-4 m-2 bg-yellow-400 rounded-md">ชำระเงิน</button>
    </center>
    <!-- <pre>{{ productId }}</pre> -->
    <div class="flex flex-wrap flex-row justify-center">
      <div
        @click="StoreProduct(product.id)"
        class="w-40 m-4 shadow-xl rounded-xl"
        v-for="(product, index) in products"
        :key="index"
      >
        <img class="rounded-xl" :src="product.image" alt="" />
        <div class="p-2">
          <h2 class="text-xl">{{ product.name }}</h2>
        </div>

        <h2 class="m-2 text-blue-500">ราคา {{ product.price }} .-</h2>
      </div>
    </div>
  </div>
</template>

<script>
import products from "@/static/product.json";
import shop from "~/components/shop.vue";
import _ from "lodash";
export default {
  components: { shop },
  data: () => {
    return {
      products: products,
      productId: [],
    };
  },

  methods: {

    async StoreProduct(id) {
      let data = _.includes(this.productId,id)
      if(!data){
      this.productId.push(id);
      }
    },
    async Gotoprice(){
        let id = this.productId.toString();
        await this.$router.push('/price?id='+id)
    },
  },
  async created() {},
};
</script>

<style>
</style>