<template>
  <div>
    <nav class="navbar navbar-light bg-black my-navbar px-2">
        <div class="container-fluid">
            <a class="navbar-brand text-danger fs-2"><img src="../assets/img/815221.png" alt="logo-netflix"></a>
            <div class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" v-model="searchInput" @keyup.enter="$emit('searchChar', searchInput)">
                <button class="btn btn-outline-success bg-danger text-white border-3  border-white" type="submit" @click="$emit('searchChar', searchInput)">Search</button>
            </div>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
    name: "IndexHeader",
    data: function(){
        return{
            searchInput : ""
        }
    }
}
</script>

<style lang="scss" scoped>
.my-navbar{
    height: 174px;
}

img{
    width: 7em;
}
</style>