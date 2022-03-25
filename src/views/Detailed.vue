<template>
<div v-if="movie" class="container">
  <img :src="imagePath + movie.backdrop_path" alt="" class="movie-image">
  <h2>{{movie.title}}</h2>
  <p>{{movie.overview}}</p>
</div>
</template>

<script>
export default {
    props: ["id"],
    data(){
        return{
            movie: null,
            // id: 823625,
            apikey: "7dd2f6061023c47cd5775913d9e60359",
            imagePath: "https://image.tmdb.org/t/p/original"
        }
    },
    mounted(){
        fetch("https://api.themoviedb.org/3/movie/" + this.id + "?api_key=" + this.apikey)
        .then(res => res.json())
        .then(data => {
            console.log(data)
            this.movie = data
        })
        .catch(err => console.log(err))
    }
}
</script>

<style>

.container{
    width: 80%;
    margin-inline: auto;
    text-align: center;
}

.movie-image{
    width: 100%;
}

</style>