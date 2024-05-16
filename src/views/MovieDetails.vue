<script>
import axios from 'axios';

export default {
  props: ['id'],
  data() {
    return {
      movie: null
    };
  },
  methods: {
    getMovieDetails() {
      axios.get(`http://127.0.0.1:8000/api/movies/${this.id}`).then(res => this.movie = res.data.movie);
    }
  },
  mounted() {
    this.getMovieDetails();
  }
}
</script>

<template>
  <div v-if="movie">
    <h1>{{ movie.title }}</h1>
    <p>Release Date: {{ movie.release }}</p>
    <p>Schedule Time: {{ movie.schedule_time }}</p>
    <!-- Add more movie details here -->
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>
