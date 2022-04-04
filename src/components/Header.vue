<template>
    <nav class="navbar navbar-light bg-light">
        <div class="container-fluid">
            <a class="navbar-brand"></a>
            <div class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" v-model="searchInput" 
                @keyup.enter="$emit('searchChar', searchInput)">
                <button class="btn btn-outline-success" type="submit"
                @click="$emit('searchChar', searchInput)">Search</button>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name : 'IndexHeader',
    data : function(){
        return{
            searchInput : ''
        }
    }
}
</script>

<style>

</style>