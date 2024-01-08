<script setup>
import { ref, onMounted, reactive } from 'vue'

const props = defineProps({
    h: {
        type: Number,
        default: 200
    }, w: {
        type: Number,
        default: 200
    },min: {
        type: Number,
        default: 0.0
    },max: {
        type: Number,
        default: 1.0
    },src: {
        type: String,
        default: "src/esp32/sys/heap"
    }
})

const maxWidth = ref('maxWidth')
maxWidth.value =  props.w
const canvas = ref(null)


onMounted(() => {
    console.log(props)
//    const canvas = document.getElementById('canvas')
    const ctx = canvas.value.getContext('2d')
    ctx.beginPath()
    ctx.arc(95, 50, 40, 0, 2 * Math.PI)
    ctx.stroke()
})


</script>
<template>
    <canvas ref="canvas" :width="w" :height="h" style="border:1px solid #000000;">
    </canvas>
</template>