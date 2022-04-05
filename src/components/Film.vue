<template>
    <div>
        <div class="my-card m-5">
            <img :src="getPoster(film.poster_path)" alt="">
            <h1>{{film.title}}</h1>
            <h2>{{film.original_title}}</h2>
            <Lang-flag  :iso ="film.original_language" />
        </div>
        <div class="my-card m-5">
            <h1>{{film.original_name}}</h1>
            <span v-for="(x, index) in star(film.vote_average)" :key="index"><font-awesome-icon icon="fa-solid fa-star" /></span>
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
        star(vote){
        return Math.ceil(vote / 2);
        }
    }
}
</script>

<style lang="scss" scoped>

</style>