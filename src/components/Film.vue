<template>
    <div>
        <div class="my-card m-5">
            <img :src="getPoster(film.poster_path)" alt="">
            <h1>{{film.title}}</h1>
            <h2>{{film.original_title}}</h2>
            <Lang-flag  :iso ="film.original_language" />
            <h3>{{film.vote_average}}</h3>
        </div>
        <div class="my-card m-5">
            <h1>{{film.original_name}}</h1>
            <h3>{{film.original_language}}</h3>
            <span v-for="(x, index) in Math.round(film.vote_average)" :key="index">*</span>
        </div>
    </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';
export default {
    name : "IndexFilm",
    props: {
        "film" : Object
    },
    components:{
        LangFlag,
    },
    methods:{
        getPoster(path){
            return `https://image.tmdb.org/t/p/w342/${path}`
        },

    }
}
</script>

<style lang="scss" scoped>
</style>