<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import { ref } from 'vue'
import PostList from './components/PostList.vue'

export default {
  name: 'Home',
  components: {
    PostList,
  },
  setup() {
    const posts = ref([
      {
        title: 'My first post',
        body: 'lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos.',
        id: 1,
      },
      {
        title: 'My second post',
        body: 'lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos.',
        id: 2,
      },
    ])

    return { posts }
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
