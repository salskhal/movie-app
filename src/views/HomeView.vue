<template>
  <div class="home">
    <h1 class="title">LASTEST MOVIES</h1>
    <div class="movie-card" >
      <div v-for="movie in movies" :key="movie.id" class="movies">
        <router-link :to="{ name: 'Detailed', params: { id: movie.id } }" :id="movie.id">
          <img
            :src="imagepath + movie.backdrop_path"
            :alt="movie.poster_path"
            class="image"
          />
          <div class="details">
          <h4>{{ movie.original_title }}</h4>
          <p class="rating">{{ movie.vote_average }}</p>
          </div>
        </router-link>
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
      imagepath: "https://image.tmdb.org/t/p/original",
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
  margin-bottom: 30px;
  font-size: 3rem;
  color: white;
}

.movie-card {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 20px;
  padding-inline: 50px;
  padding-bottom: 20px;
}

.movie-card a{
  text-decoration: none;
  color: white;
}

@media screen and (max-width: 900px) {
  .movie-card {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media screen and (max-width: 700px) {
  .movie-card {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (max-width: 500px) {
  .movie-card {
    grid-template-columns: 1fr;
  }
}

.movies {
  cursor: pointer;
  transition: all 0.2s ease-in-out;
  background: #053854;
  border-radius: 10px;
  overflow: hidden;
}

.movies:hover {
  transform: scale(1.005);
}

.image {
  width: 100%;
}

.details{
  padding: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.rating{
  padding: 10px;
  border-radius: 10px;
  background: #06476B;
}
</style>
