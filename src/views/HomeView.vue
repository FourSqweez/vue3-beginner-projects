<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue'
import { ref } from 'vue'

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
    const showPosts = ref(true)

    return { posts, showPosts }
  },
}
</script>

<style>
button {
  background-color: #42b983;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 20px;
  margin-right: 10px;
}
</style>
