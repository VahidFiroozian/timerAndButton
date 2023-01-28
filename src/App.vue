<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Timer from './components/Timer.vue'
import {ref} from "vue"

const isWorking = ref(true)

const changeToButton = (isFinished) => {
  console.log("dakhele App")
  isWorking.value = false
}

</script>

<template>

  <main>
    <div v-if="isWorking">
      <Timer @selectedValue = "changeToButton"/>
    </div>
    <div v-else>
      <button>click</button>
    </div>
  </main>
</template>

<style scoped>
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
  button {
    size: 40vw;
  }
}
</style>
