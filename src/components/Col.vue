<script setup>
import { ref, onMounted,reactive } from 'vue'
const props = defineProps({h: Number, w: Number})

</script>
<template>
    <div class="vertical" :width="w" >
        width : {{  w  }}
        Let's place here a very loooooooooooooooooooooooooooooooooooooooooooong text
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
}   
.vertical {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    height: 100%;
    max-width: 100px;
}
</style>
