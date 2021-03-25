<template>
  <div class="flex bg-yellow-300 w-24 p-4 rounded-full">
      <img class="h-13 w-13" src="https://www.flaticon.com/svg/vstatic/svg/3144/3144456.svg?token=exp=1616402261~hmac=f80edc8da47b7a15d2ef82257db071e0" alt="">
      <h1>{{count}}</h1>
  </div>
</template>

<script>
export default {
    props:{
        count:{
            default:0
        }
    }

}
</script>

<style>

</style>