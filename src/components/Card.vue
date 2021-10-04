<template>
    <div class="col-12 col-md-4 col-lg-2 p-3 m-3">
        <div class="description">
            <h1>{{propMovie.title}}</h1>
            <h2>{{propMovie.original_title}}</h2>
            <h2>{{propMovie.vote_average}}</h2>

            <img v-if="propMovie.original_language== 'en'" src="../assets/en-flag.jpg" alt="propMovie.original_language">
            <img v-else-if="propMovie.original_language == 'it'" src="../assets/ita-flag.jpg" alt="propMovie.original_language">
            <h2 v-else>{{propMovie.original_language}}</h2>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Cards',
    props: ["propMovie"]
}
</script>

<style lang='scss' scoped>

.description{
    color: white;
    text-align: center;
    img{
        width: 50px;
        border-radius: 12px;
    }
}


</style>