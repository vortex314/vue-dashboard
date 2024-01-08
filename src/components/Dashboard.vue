<script setup>
import { ref, onMounted,reactive } from 'vue'

const props = defineProps({h: Number, w: Number})

</script>
<template>
    <div :height="h" :width="w">
        <p> height : {{ h }} width : {{ w }}</p>
        <slot>Fallback slot for Dashboard</slot>
    </div>
</template>