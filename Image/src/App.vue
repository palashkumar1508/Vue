<script setup>
import {ref}  from  'vue'
let imag = ref("https://www.gannett-cdn.com/presto/2021/03/22/NRCD/9d9dd9e4-e84a-402e-ba8f-daa659e6e6c5-PhotoWord_003.JPG?width=660&height=425&fit=crop&format=pjpg&auto=webp")


 
</script>

<template>

    <div class=" w-full flex flex-col text-white gap-4 justify-center p-10 items-center rounded-lg m-4 mr-4">
        <h1>Direct  image in template</h1>
        <img src="./assets/image/part-blurry-image.webp" alt="" width="400" height="400">
        <img src="https://jes.edu.vn/wp-content/uploads/2017/10/h%C3%ACnh-%E1%BA%A3nh.jpg" alt="" width="400" height="400">
        
        <h1>indirect Image from script</h1>
        <img :src=" imag " width="400" height="400" alt="">

    </div>
    
</template>

