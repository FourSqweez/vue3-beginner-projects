<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search" />
    <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      <p>{{ name }}</p>
    </div>
    <button @click="handleStop">Stop</button>
  </div>
  <router-view />
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'luigi', 'yoshi', 'toad', 'peach'])

    const stopWatch = watch(search, () => {
      console.log('watch function run')
    })

    const stopEffect = watchEffect(() => {
      console.log('watchEffect function run', search.value)
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const handleStop = () => {
      stopWatch()
      stopEffect()
    }

    return { names, search, matchingNames, handleStop }
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
