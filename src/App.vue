<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} is {{ ninjaOne.age }} years old</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} is {{ ninjaTwo.age }} years old</p>
    <button @click="updateNinjaTwo">Update ninja two</button>
  </div>
  <router-view />
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    const ninjaOne = ref({
      name: 'mario',
      age: 30,
    })

    const ninjaTwo = reactive({
      name: 'luigi',
      age: 35,
    })

    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }

    const updateNinjaTwo = () => {
      ninjaTwo.age = 40
    }

    return { ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.test {
  color: red;
}
</style>
