<template>
  <div v-if="job" class="job-details">
    <h1>Job Details</h1>
    <h2>{{ job.title }}</h2>
    <p>{{ job.details }}</p>
  </div>
</template>

<script>
export default {
  name: 'JobDetails',
  props: ['id'],
  data() {
    return {
      jobs: [
        {
          title: 'Software Engineer',
          id: 1,
          details:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos.',
        },
        {
          title: 'Software Engineer',
          id: 2,
          details:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos.',
        },
        {
          title: 'Software Engineer',
          id: 3,
          details:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quos.',
        },
      ],
    }
  },
  computed: {
    job() {
      return this.jobs.find((job) => job.id === parseInt(this.id))
    },
  },
  created() {
    if (!this.job) {
      this.$router.push({ name: 'not-found' })
    }
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
