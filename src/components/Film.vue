<template>
    <div>
        <div>
            <img :src="getPoster(Film.poster_path)" alt="">
            <img :src="getPoster(Film.backdrop_path)" alt="">
            <h2>{{Film.original_title}}</h2>
            <h1>{{Film.title}}</h1>
        </div>
        <!--SerieTv-->
        <div>
            <h1>{{Film.name}}</h1>
            <h2>{{Film.original_name}}</h2>
            <h3>{{Film.original_language}}</h3>
            <h3>{{Film.vote_average}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name : 'IndexFilm',
    props : {
        'Film' : Object
    },
    computed : {
        lingua(linguaScelta){
            if (linguaScelta == "en"){
                return "🇮🇹"
            }else{
                return "🇬🇧"
            }
        }
    },
    methods: {
        getPoster(path){
            return `https://image.tmdb.org/t/p/w300/${path}`;
        }
    }
}
</script>

<style lang="scss" scoped>

</style>