<script>
import axios from "axios"

export default {
  data() {
    return {
      posts: []
    }
  },
  mounted() {
    axios.get('https://jsonplaceholder.typicode.com/posts?_limit=5')
      .then(response => {
        // handle success
        console.log(response.data)
        this.posts = [...response.data]
      });
  }
}
</script>

<template>
  <div v-for="p in posts">
    <h2>{{ p.title }}</h2>
    <p>{{ p.body }}</p>
  </div>
</template>

<style scoped></style>
