<script>
import axios from 'axios';
export default {
  data(){
    return{
      url : 'http://127.0.0.1:8000/api/movies',
      moviesArray : [],
    }
  },
  methods: {
    getMovies(){
      axios.get(this.url).then(res => this.moviesArray = res.data.movies);
    }
  },
  mounted(){
    this.getMovies();
  }
}
</script>

<template>
  <main class="text-center min-h-screen">
<h1 class="my-5 text-3xl font-semibold uppercase">welcome in our Homepage</h1>
<div class="mx-auto container flex flex-wrap justify-center mt-20 gap-2">
  <div v-for="item in moviesArray" :key="item.id" class="card w-80 h-96 flex flex-col justify-center border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
    <h1 class="p-2 font-bold text-2xl">{{ item.title }}</h1>
    <span class="block p-2">Uscita {{ item.release }}</span>
    <span class="block p-2">Orari: {{ item.schedule_time }}</span>
    <router-link :to="{ name: 'MovieDetails', params: { id: item.id } }" class="w-4/5  mx-auto bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 border border-red-700 rounded">
          View Details
        </router-link>
  </div>

</div>
  </main>
</template>
