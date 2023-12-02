<script setup>

import Api from './Api.vue'


</script>

<template>
<div class="flex flex-col justify-center items-center">
  <div class="bg-black w-full">
        <h1 class="flex items-center justify-center text-white  mb-10 mt-10 font-serif text-center px-2 text-2xl md:p-0 md:text-4xl">INSTITUTO TECNÓLOGICO SUPERIOR DE MOTUL</h1>
      </div>
      <div class="flex flex-row mb-5">
        <img src="../assets/LOGO.svg" alt="logotipo del sitmotul" class="w-16 md:w-20 mx-auto mt-4 mb-4">
        <h2 class="flex justify-center items-center text-white  mt-5 mb-5 text-3xl md:text-4xl font-bold">SITMOTUL</h2>
      </div>
       
    
  <div class="bg-white  rounded-lg mb-10 w-11/12 p-4 md:w-1/2 md:p-10">
    <Api></Api>
    
  </div>
</div>
</template>