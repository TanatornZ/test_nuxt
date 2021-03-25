<template>
  <div>
      <h1 class="m-4 text-xl ">รายการสินค้าทั้งหมด</h1>
      <div class="flex ml-5 mb-2" v-for="product,index in listProduct" :key="index">
          {{product.name}}
          {{product.price}}
          <input class="ml-5" type="text" v-model="product.count" placeholder="จำนวน">
          {{product.price * product.count}}

      </div>
        <h1> ราคาทั้งหมด {{calculate()}}</h1>
      <center>
      <button class="mt-5 bg-yellow-500 w-20 h-12 rounded-md">ชำระเงิน</button>
      </center>
  </div>
</template>

<script>
import products from "@/static/product.json";
import _ from 'lodash'
export default {
    data:() => {
        return ({
            listProduct:[],
            ids:null
        })
    },
    methods:{
        calculate(){
            let allPrice = 0 ;
            for (let index = 0; index < this.listProduct.length; index++) {
                allPrice += this.listProduct[index].price*this.listProduct[index].count
                
            }
            return allPrice;
        }
    },
    async created(){
        let ids = this.$route.query.id
        this.ids = ids.split(',')
        console.log(this.ids)

        for (let index = 0; index < this.ids.length; index++) {

            let product = _.find(products,{id:Number(this.ids[index])})
            console.log(product)

            if(product){
                product.count = 1
                this.listProduct.push(product);
            }
        }

        
    }
}
</script>

<style>

</style>