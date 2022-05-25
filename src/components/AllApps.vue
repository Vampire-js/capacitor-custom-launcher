<template>

</template>

<script setup>
import {ref} from 'vue'
const props = defineProps({isToggled:Boolean});
const topVal = ref(0);

if(props.isToggled == true){
topVal.value = 0
}else{
    topVal.value = 100
}

</script>