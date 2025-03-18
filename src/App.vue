<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and I am {{ age }} years old</p>
    <button @click="handleClick">Click me</button>
    <button @click="age++">Increase age</button>
    <input type="text" v-model="name" />
  </div>
  <router-view />
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    let name = ref('mario')
    let age = ref(30)

    // const p = ref(null)

    const handleClick = () => {
      name.value = 'luigi'
      age.value = 40
    }

    return { name, age, handleClick }
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
