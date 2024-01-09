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
    <canvas class="canvas" ref="canvas" :width="w" :height="h" />
</template>
<style scoped>
.canvas {
    border: 1px solid #2ddeeb;
    background-color: #f1f1f1;
    padding: 0px;
    margin: 0px;
    word-wrap: break-word;
    overflow: hidden;
    inline-size:min-content;
}
</style>