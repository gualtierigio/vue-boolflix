<template>
    <div class="col-12 col-md-4 col-lg-2 p-3 m-3">
        <div class="description">
            <h3>{{propMovie.title}}</h3>
            <h5>{{propMovie.original_title}}</h5>
            <h5>{{propMovie.vote_average}}</h5>

            <img v-if="propMovie.original_language== 'en'" src="../assets/en-flag.jpg" alt="propMovie.original_language">
            <img v-else-if="propMovie.original_language == 'it'" src="../assets/ita-flag.jpg" alt="propMovie.original_language">
            <h5 v-else>{{propMovie.original_language}}</h5>
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
@import '../style/variables.scss';

.description{
    color: white;
    text-align: center;
    background-color: $main-color;
    padding: 10px;
    img{
        width: 50px;
        border-radius: 12px;
    }
}


</style>