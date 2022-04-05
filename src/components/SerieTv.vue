<template>
  <div>
    <div class="my-card animate__animated animate__zoomIn rounded-3 p-2 bg-gradient">
            <img :src="getPoster(serie.poster_path)" alt="locandina-serie-tv">
            <div class="info animate__animated animate__flip">
                <span class="fs-5 text-white">Titolo:</span> <span class="fs-5 fw-bolder text-danger">{{serie.name}}</span> <br>
                <span class="fs-5 text-white">Titolo originale:</span> <span class="fs-6 fw-bolder text-danger">{{serie.original_name}}</span> <br>
                <span class="text-white">Lingua:</span> <Lang-flag  :iso ="serie.original_language" /> <br>
                <div id="overflow"><span class="fs-3 text-white">Overview:</span><p class="fw-bolder text-danger">{{serie.overview}}</p></div>
                <span class="text-white">Voto: </span>
                <span v-for="(x, index) in star(serie.vote_average)" :key="index" class="info">
                    <font-awesome-icon icon="fa-solid fa-star" />
                </span>
            </div>
        </div>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';
import 'animate.css';
export default {
    name : 'IndexSerieTv',
    props: {
        'serie' : Object
    },
    components:{
        LangFlag
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

<style scoped>
img + .info{
    display: none;
}

.my-card:hover img{
    display: none;
}

.my-card:hover img + .info{
    display: block;
}

.d-none{
    display: none;
}

.fa-star{
    color: yellow;
}

.my-card{
    border: 3px solid red;
    cursor: pointer;
    width: 100%;
}

.my-card img{
    width: 100%;
    height: 100%;
}

.info #overflow{
    height: 350px;
    overflow: scroll;
}
.info.animate__animated.animate__flip{
    --animate-duration: 1s;
}

.my-card.animate__animated.animate__zoomIn{
    --animate-duration: 1.5s;
}
</style>