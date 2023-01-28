<template>
    <div>
        <p>{{second}}</p>
    </div>
</template>

<script setup>
import { ref} from "vue"
    const second = ref(5);
    const emit = defineEmits(["selectedValue"])
    const isFinished = ref(false)

    const emitValue = (isFinished) => {
        console.log(isFinished.value)
        emit("selectedValue",isFinished)
    }
    
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
        else {
            console.log("dokmeh")
            emitValue(isFinished)
        }
    }
    timer()
   
</script>

<style scoped>
  p{
    font-size: 20rem;
  }
</style>