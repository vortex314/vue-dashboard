<script setup>
import { ref, onMounted,reactive } from 'vue'
const props = defineProps({h: Number, w: Number})

</script>
<template>
    <div :height="h" class="flex">
        <slot>Fallback slot for Row</slot>
    </div>
</template>

<style scoped>
div {
    border: 4px solid #2ddeeb;
    background-color: #f1f1f1;
    padding: 10px;
    margin: 1px;
    word-wrap: break-word;
    overflow: hidden;
    inline-size:min-content;
}
.flex {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: stretch;
    align-content: stretch;
}
</style>
