<template>

    <div class="h-auto bg-yellow-500 flex flex-wrap justify-center items-center">

     <div class="w-1/3">
        <button @click="menu =! menu" class="ml-4">menu</button>
     </div>
     <div class="w-1/3">
        <center class="text-xl text-white">HomePage</center>
     </div>
     <div class="w-1/3 flex justify-end">
        <button class="mr-4">Profile</button>
     </div>

     <div v-if="menu" class="w-full flex flex-col justify-center items-center">
        
         <button class="p-2 m-2 text-white hover:bg-gray-400">menu1</button>
         <button class="p-2 m-2 text-white hover:bg-gray-400">menu2</button>
         <button class="p-2 m-2 text-white hover:bg-gray-400">menu3</button>
         <button class="p-2 m-2 text-white hover:bg-gray-400">menu4</button>
        
     </div>
     </div>





  <!-- <div class="h-15 bg-yellow-500">

   <h2 class="text-x1 md:text-4xl">{{head}}</h2> 
    <h2>{{text}}</h2>                        //การเรียกใช้ text 

  </div> -->
</template>

<script lang="ts">
export default {

    props:{                                 //การรับค่าจากข้องนอก
        head:{
            default:"Header"
        },
        username:{
            default : ''
        },
        loginded:{
            default : false
        }
    },

    data:() => {                            //เก็บตัวแปรทั้งหมด
        return ({                           
            text:'Hello',
            menu:false,
        })
    },                                      // อย่าลืม ,
    methods:{                               //การทำงาน


    },
    async created(){

    }

}
</script>

<style>

</style>