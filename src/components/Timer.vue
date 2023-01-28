<template>
    <div>
        <button @click="timer()">click</button>
        {{second}}
    </div>
</template>

<script setup>
import {onMounted, onUpdated, ref, watch} from "vue"
    const second = ref(5);
    console.log("salam")
    
    const timer = () => {
        console.log("baz dobare")
        if(second.value > 0){
                console.log(second.value)
                setTimeout(() => {
                    second.value--
                    console.log(second.value)
                    timer()}
                    ,1000)   
                    
                    
                }
    }
    timer()
    


   
</script>