<template>
    <div>
        <h1>{{Film.title}}</h1>
        <h2>{{Film.original_title}}</h2>
        <h3>{{Film.original_language}}</h3>
        <h3>{{Film.vote_average}}</h3>
    </div>
</template>

<script>
export default {
    name : "IndexFilm",
    props: {
        "Film" : Object
    }
}
</script>

<style lang="scss" scoped>

</style>