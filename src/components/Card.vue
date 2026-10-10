<script setup>
    import {defineProps} from 'vue';

    defineProps({
        bg: {
            type: String,
            default: 'bg-gray-100'
        }
    }) 
</script>

<!-- If you are using bacticks it means there is actual javascript code in the template, so you need to use v-bind:class to bind the class dynamically. -->

<template>
    <div :class="`${bg} p-6 rounded-lg shadow-md`">  
        <slot></slot> <!-- A slot is like a little window: it lets the content between <Card> and </Card> show up inside the card. -->
    </div>
</template>