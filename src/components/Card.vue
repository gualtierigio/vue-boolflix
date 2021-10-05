<template>
    <div class="col-12 col-md-4 col-lg-3 mb-4">
        <div class="description">
            <div>
                <img class="img-fluid poster" :src="urlBase+propMovie.poster_path" alt="Movie poster">
            </div>
            <h3>{{propMovie.title}}</h3>
            <h5>{{propMovie.original_title}}</h5>
            <h5>{{propMovie.vote_average}}</h5>
            <div class="avarange-vote mb-2">
                <div class="stars">
                    <i class="fas fa-star"></i>
                </div>
                <div class="stars">
                    <i class="far fa-star"></i>
                </div>
            </div>

            <img class="flag" v-if="propMovie.original_language== 'en'" src="../assets/en-flag.jpg" alt="propMovie.original_language">
            <img class="flag" v-else-if="propMovie.original_language == 'it'" src="../assets/ita-flag.jpg" alt="propMovie.original_language">
            <h5 v-else>{{propMovie.original_language}}</h5>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Cards',
    props: ["propMovie"],
    data() {
        return {
            urlBase: 'https://image.tmdb.org/t/p/w342'
        }
    },
    methods: {
        stars() {
            Math.ceil.(propMovie.vote_average)
        }
    }
}
</script>

<style lang='scss' scoped>
@import '../style/variables.scss';
@import '../style/general.scss';

.description{
    color: white;
    text-align: center;
    background-color: $main-color;
    padding: 5%;
}

.poster{
     width: 350px;
}
.flag{
    width: 50px;
    height: 35px;
    border-radius: 12px;
}

.stars{
    display: inline-block;
}


</style>