<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and I am {{ age }} years old</p>
    <button @click="handleClick">Click me</button>
  </div>
  <router-view />
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    let name = 'mario'
    let age = 30

    const p = ref(null)

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      p.value.textContent = 'hello world'
    }

    return { name, age, handleClick, p }
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
