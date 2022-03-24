<template>
<div v-if="movie">
  <h1>Detailed {{ id }}</h1>
</div>
</template>

<script>
export default {
    props: ["id"],
    data(){
        return{
            movie: null,
            // id: 823625,
            apikey: "7dd2f6061023c47cd5775913d9e60359"
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

</style>