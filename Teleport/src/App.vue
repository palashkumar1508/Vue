<script setup>
import Teleportss from './Teleport.vue';
import Outside from './Outside.vue'
 
</script>

<template>

    <div class=" w-full flex flex-col gap-4 justify-center p-10 items-center rounded-lg m-4 mr-4">
        <Teleportss/>
        <h1 class="bg-black text-white p-4 rounded-b-xl shadow-2xl text-3xl shadow-cyan-400">Without Teleport !</h1>
        <Outside />

        <h1 class="bg-black text-white p-4 rounded-b-xl shadow-2xl text-3xl shadow-cyan-400">With Teleport ! with tag </h1>
        <teleport to="body">
            <Outside/>
            <h1 class="text-cyan-500">I am  in body and outside the #app </h1>
        </teleport>


        <h1 class="bg-black text-white p-4 rounded-b-xl shadow-2xl text-3xl shadow-cyan-400">With Teleport ! with Id </h1>
        <teleport to="#teleport">
            <h1 class="text-cyan-500">I am  in body and insidethe div of id- teleport </h1>
            <Outside/>
        </teleport>

        
    </div>
    
</template>

