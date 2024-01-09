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
    border: 1px solid #2ddeeb;
    background-color: #f1f1f1;
    padding: 0px;
    margin: 0px;
    word-wrap: break-word;
    overflow: hidden;
    inline-size:min-content;
    width: 100%;
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
