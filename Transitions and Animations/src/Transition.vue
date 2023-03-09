<template>
   <div class="w-3/4 p-3 rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <h1 class="justify-center flex h-14 items-center font-bold text-2xl">Transition</h1>
        <h3> $$ Transitions are a way to add animations to elements when they are added, updated, or removed from the DOM. They allow you to add some visual feedback to your application, making it more engaging and user-friendly. Transitions in Vue.js Composition API are similar to those in the Options API, but the syntax is slightly different.</h3>
        <br>
        <h2>How to Use Transitions in Vue.js Composition API?</h2>
        <h3>**To use transitions in Vue.js Composition API, we need to import the defineTransition function from the vue package. We can then define a transition by calling this function and passing in an object with the necessary configuration options.</h3>
        <div class="flex justify-center items-center m-2">
            <div class="w-3/4 p-3 rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
            <h1 class="justify-center flex h-14 items-center font-bold text-2xl">Example</h1>
            <h3> <pre>Example of how to define a simple transition:
import { defineTransition } from 'vue';

const fadeTransition = defineTransition({
  enter(el, done) {
    el.style.opacity = 0;
    setTimeout(() => {
      el.style.transition = 'opacity 0.5s';
      el.style.opacity = 1;
      done();
    }, 0);
  },
  leave(el, done) {
    el.style.transition = 'opacity 0.5s';
    el.style.opacity = 0;
    setTimeout(() => done(), 500);
  },
});</pre>
            </h3>
            <h3>In this example, we define a transition called fadeTransition that fades in elements when they are added and fades out elements when they are removed. The enter function is called when an element is added to the DOM, and the leave function is called when an element is removed from the DOM.
            </h3>
            <h3>The enter function takes two arguments: the element being added (el) and a callback function (done) that needs to be called when the transition is complete. In this case, we set the opacity of the element to 0, and then use a setTimeout function to delay the transition by 0 milliseconds (to allow the browser to apply the initial styles). We then set the transition property to opacity 0.5s and the opacity to 1, which fades in the element. Finally, we call the done callback to signal that the transition is complete.</h3>
            <h3>The leave function is similar, but instead of fading in the element, we fade it out by setting the opacity to 0. We then use a setTimeout function to delay calling the done callback by 500 milliseconds (the duration of the transition).
            </h3>
            <h3>Once we have defined our transition, we can use it in our Vue components by adding the v-transition directive to the element we want to animate:</h3>
            <h3><pre>
  (div v-for="item in items" :key="item.id"
   v-transition="fadeTransition" )
    {item.text} (/div)
</pre></h3>
            </div>
        </div>
        <br>
        <h3>Transition is a built-in component : this means it is available in any component's template without having to register it . It can be used to apply enter and leave animation on elements or components passed to it via its deault slot. The enter or leave can be triggeteal by one of the following :    
        </h3>
   </div>

   <div class="w-3/4 p-3 rounded-lg bg-black shadow-lg shadow-black">
        <span class="text-teal-400">Conditional rendering vie V-if </span>
    </div>

    <div class="w-3/4 p-3 rounded-lg bg-black shadow-lg shadow-black">
        <span class="text-teal-400">Conditional rendering vie V-show </span>
    </div>

    <div class="w-3/4 p-3 rounded-lg bg-black shadow-lg shadow-black">
        <span class="text-teal-400">Dynamic components toggling via the Component's Special element </span>
    </div>

    <div class="w-3/4 p-3 rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <h1 class="justify-center flex h-14 items-center font-bold text-2xl">Transition Classes</h1>
        <h3>
            <span>v-enter-from : </span> Starting state for enter. Added before the element is inserted removed one frame after the element is inserted
        </h3>
        <h3>
            <span>v-enter-active : </span> Active state for enter. Applied during the entire entering phase. Added before the element is inserted, removed when the transition/animation finishes. This class can be ued to define the duration, delay and easing curve for the entering transition.
        </h3>
        <h3>
            <span>v-enter-to : </span> Ending State for enter. Added frame after the elemment is inserted (at the same time v-enter-from is removed ), removed when the transition/anim,animation finishes.
        </h3>
        <h3>
            <span>v-enter-to : </span> Ending State for enter. Added frame after the elemment is inserted (at the same time v-enter-from is removed ), removed when the transition/anim,animation finishes.
        </h3>
   </div>

   <div class="w-3/4 p-3 flex flex-col justify-center items-center rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <button @click="show=!show" class="border-2 border-teal-500 text-teal-400 p-3 rounded-xl m-3 ">Click</button>
        <Transition>
            <h1 class="bg-teal-500 text-white p-4 rounded-sm" v-if="show">Transition</h1>
        </Transition>
   </div>

   <div class="w-3/4 p-3 flex flex-col justify-center items-center rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <h1>Named Transition</h1>
        <h3>[] In Named transition we get a name attribute and we have to change the v- to that name given to the transition attribute name</h3>
        <button @click="nshow=!nshow" class="border-2 border-teal-500 text-teal-400 p-3 rounded-xl m-3 ">Click</button>
        <Transition name="fade">
            <h1 class="bg-teal-500 text-white p-4 rounded-sm" v-if="nshow">Transition</h1>
        </Transition>
   </div>

   <div class="w-3/4 p-3 flex flex-col justify-center items-center rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <h1>Custom Transition Classes</h1>
        <h3>[]It is used for the 3rd party Library</h3>
        <button @click="cshow=!cshow" class="border-2 border-teal-500 text-teal-400 p-3 rounded-xl m-3 ">Click</button>
        <Transition name="fade">
            <h1 class="bg-teal-500 text-white p-4 rounded-sm" v-if="cshow">Transition</h1>
        </Transition>
   </div>

   <div class="w-3/4 p-3 rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <h1 class="justify-center flex h-14 items-center font-bold text-2xl">Transition Group</h1>
        <h3> [Transitiongroup] is a built-in component designed for animating the insertion, removal, and order change of elements or components that are rendered in a list.
        </h3>
        <h3>[Transitiongroup] supports the sa,e props, CSS transition classes, and JavaScript hoo listeners as (Transition)
        </h3>
   </div>

   <div class="w-3/4 p-3 rounded-lg bg-black text-teal-400 border-2 border-teal-400 shadow-lg shadow-black">
        <h1 class="justify-center flex h-14 items-center font-bold text-2xl">Transition vs Transition Group</h1>
        <h3>*By Default, it doesn't render a wrapper element. But you can specify an element to be rendered with the tag prop
        </h3>
        <h3>*Transition Modes are not available, because we are non longer altering between mutually exclusive elements.
        </h3>
        <h3>
            *Element inside are always required to have a unique key attribute.
        </h3>
        <h3>*CSS transition classes will be applied to individual elemens in the list, not to the group / container itself.
        </h3>
   </div>

</template>
<script setup>
import {ref}  from 'vue'
    let show = ref(true)
    let nshow = ref(true)
    let cshow = ref(true)

</script>



<style scoped>
    span{
        @apply p-2 shadow-sm shadow-teal-400
    }
    h3{
        @apply my-2
    }

    .v-enter-active,
    .v-Leave-active{
        transition: opacity 1.9s ease;
    }

    .v-enter-from,
    .v-Leave-to{
        opacity: 0;
    }

    .fade-enter-active,
    .fade-Leave-active{
        transition: opacity 1.9s ease;
    }

    .fade-enter-from,
    .fade-Leave-to{
        opacity: 0;
    }
</style>

