<template>
  <div class="home">
    <h1 class="title">MOVIES</h1>
    <div class="movie-card">
      <div v-for="movie in movies" :key="movie.id" class="movies">
        <img :src="imagepath + movie.backdrop_path" :alt="movie.poster_path" class="image">
        <h4>{{ movie.original_title }}</h4>
        <p>{{}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movies: [],
      apikey: "7dd2f6061023c47cd5775913d9e60359",
      imagepath: "https://image.tmdb.org/t/p/original"
    };
  },
  mounted() {
    fetch(
      `https://api.themoviedb.org/3/movie/popular?api_key=${this.apikey}&language=en-US`
    )
      .then((res) => res.json())
      .then((data) => {
        this.movies = data.results;
      });
  },
};
</script>



<style>
.title {
  text-align: center;
}

.movie-card{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 20px;
  padding-inline: 50px;
}

.movies{
  cursor: pointer;
  transition: all .2s ease-in-out
}

.movies:hover{
  transform: scale(1.05);
}


.image{
  width: 100%
}
</style>
