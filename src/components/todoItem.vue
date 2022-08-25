<script setup>
import {computed, ref} from 'vue';
const props = defineProps({
    done: Boolean,
    content: String,
    children: Array
})
const done = ref(props.done);
const content = ref(props.content)
const children = ref(props.children)

const marginBottom = children.value[0]? 'mb-4' : '';

</script>

<template>
<div 
class="w-full border border-black p-4"
:class="marginBottom"
>
    <div 
    class="w-full border-border-black flex items-center gap-4"
    :class="marginBottom"
    >
        <input 
        class="border border-black outline-none" 
        type="text" 
        name="" 
        id=""
        v-model="content"
        >

        <button
        class="bg-red-300 py-2 px-4 font-bold"
        > Hello </button>

        <p
        
        > {{content}} </p>

        <input 
        class="w-8 h-8 text-red-300"
        type="checkbox" name="" id="" :checked="done" disabled>
    </div>

    <todoItem v-for="task in children" 
    :key="(Math.random().toString(36).substring(2))"
    v-bind="task" />

</div>
    
</template>