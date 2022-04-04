<template>
    <div>
        <div class="my-card m-5">
            <img :src="getPoster(film.poster_path)" alt="">
            <h1>{{film.title}}</h1>
            <h2>{{film.original_title}}</h2>
            <h3>{{film.original_language}}</h3>
            <h3>{{film.vote_average}}</h3>
        </div>
        <div class="my-card">
            <h1>{{film.original_name}}</h1>
            <h3>{{film.original_language}}</h3>
            <h3>{{film.vote_average}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name : "IndexFilm",
    props: {
        "film" : Object
    },
    methods:{
        getPoster(path){
            return `https://image.tmdb.org/t/p/w342/${path}`
        }
    }
}
</script>

<style lang="scss" scoped>
</style>