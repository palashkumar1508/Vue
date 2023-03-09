<script setup >
import {ref}  from 'vue'
import Guest from './Guest.vue';
import Popular from './Popular.vue';
import Recent from './Recent.vue';
let post = ref();

const tabs = {
    Recent,
    Guest,
    Popular
}

</script>

<template>
    <div class="bg-black w-3/4 flex justify-center shadow-lg shadow-yellow-500 rounded-md items-center flex-col p-4 text-yellow-100 border-2 border-yellow-400">
        <h1 class="text-2xl ">Dynamic Components</h1><br>
        <h3 class="text-xl">A dynamic component is a Vue.js component that can be dynamically created and destroyed based on the user's actions or other conditions. With dynamic components, you can render different components based on the data or state of your application.</h3>
        <br>
        <h2 class="text-xl">In Vue.js, there are two ways to create dynamic components: using the v-if directive or using the built-in dynamic component feature. In this article, we'll focus on the latter.</h2>

        <div class="bg-black m-2 w-3/4 flex justify-center shadow-md shadow-yellow-500 rounded-md items-center flex-col p-4 text-yellow-100 border-2 border-yellow-400">
            <h1 class="text-2xl ">Vue's {Components} element with the special <span class="bg-yellow-100 text-black px-3">is</span> attribute</h1><br>
            <h3>The value passed to <span class="bg-yellow-100 text-black px-2">: is</span> can contain either:</h3>
            <div>
                <h3 class="text-xl">* The Name string of a registered component</h3>
                <h2 class="text-xl">* The actual imoprted component project</h2>
            </div>
            <div class="bg-black m-2 w-3/4 flex justify-center shadow-sm shadow-yellow-500 rounded-md items-center flex-col p-4 text-yellow-100 border-2 border-yellow-400">
                <h1 class="text-2xl ">Example</h1><br>
                <h3>{component :is="tabs[currentTab]"} {/component}</h3>
                
            </div>
        </div>
    </div>

    <div class="w-full">
        <div class="bg-black w-3/4 flex mx-auto my-8 justify-center shadow-lg shadow-yellow-500 rounded-md items-center flex-col p-4  border-2 border-yellow-400">
        <h1 class="text-2xl text-yellow-400">Without Dynamic Components</h1><br>
        <div class="">
            <button @click="post = 'recent'" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black" >Recent</button>
            <button @click="post = 'popular'" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black">Popular</button>
            <button @click="post = 'guest'" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black">Guest</button>
            <button @click="post = ''" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black">Hide All</button>
        </div>
    
            <Guest v-if="post === 'guest' "/>
            <Popular v-if="post === 'popular' "/>
            <Recent v-if="post === 'recent' "/>
            
        </div>
    </div>

    <div class="w-full">
        <div class="bg-black w-3/4 flex mx-auto my-8 justify-center shadow-lg shadow-yellow-500 rounded-md items-center flex-col p-4  border-2 border-yellow-400">
        <h1 class="text-2xl text-yellow-400">With Dynamic Components</h1><br>
        <div class="">
            <!-- <button @click="post = 'Recent'" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black" >Recent</button>
            <button @click="post = 'Popular'" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black">Popular</button>
            <button @click="post = 'Guest'" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black">Guest</button> -->
            <button class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black" v-for="(_,tab) in tabs" :key="tab" @click="post = tab">{{ tab }}</button>
            
            <button @click="post = ''" class="bg-yellow-300 p-3 m-3 rounded-lg border-2 border-black">Hide All</button>
        </div>
            <component :is="tabs[post]" />
            
        </div>
    </div>


    


</template>

