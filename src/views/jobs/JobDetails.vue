<template>
  <div v-if="job" class="job-details">
    <h1>Job Details</h1>
    <h2>{{ job.title }}</h2>
    <p>{{ job.description }}</p>
  </div>
  <div v-else>
    <h1>Job Details</h1>
    <p>Job not found</p>
  </div>
</template>

<script>
export default {
  name: 'JobDetails',
  props: ['id'],
  data() {
    return {
      job: null,
    }
  },
  mounted() {
    fetch(`http://localhost:3000/jobs/${this.id}`)
      .then((res) => res.json())
      .then((data) => (this.job = data))
      .catch((err) => console.log(err.message))
  },
}
</script>

<style scoped>
.job-details {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  color: #42b983;
  margin-bottom: 20px;
}

h2 {
  color: #2c3e50;
  margin-bottom: 15px;
}

p {
  color: #666;
  line-height: 1.6;
}
</style>
