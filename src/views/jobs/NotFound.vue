<template>
  <div class="not-found">
    <h1>404</h1>
    <h2>Page Not Found</h2>
    <p>Sorry, the page you are looking for does not exist.</p>
    <router-link to="/" class="home-link">Go back to Home</router-link>
  </div>
</template>

<script>
export default {
  name: 'NotFound',
}
</script>

<style scoped>
.not-found {
  text-align: center;
  padding: 50px 20px;
  max-width: 600px;
  margin: 0 auto;
}

h1 {
  font-size: 120px;
  color: #42b983;
  margin: 0;
  line-height: 1;
}

h2 {
  font-size: 32px;
  color: #2c3e50;
  margin: 20px 0;
}

p {
  color: #666;
  margin: 20px 0;
  font-size: 18px;
}

.home-link {
  display: inline-block;
  padding: 12px 24px;
  background-color: #42b983;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.home-link:hover {
  background-color: #3aa876;
}
</style>
