<template>
    <div class="col-12 col-md-4 col-lg-3 mb-4 position-relative">
        <div class="beyond-poster">
            <img v-if="propSeries.poster_path" class="poster" :src="urlBase+propSeries.poster_path" alt="Soap poster">
            <img v-else  class="poster" src="https://via.placeholder.com/342x458" alt="Series poster">
        </div>
        <div class="description position-absolute">
            <h1>Title: {{propSeries.name}}</h1>
            <h5>Original title: {{propSeries.original_name}}</h5>
            <div class="d-flex justify-content-between">
                <h3>Stars:</h3>
                <div class="avarange-vote mb-2">
                    <div class="stars">
                        <i v-for="i in stars(propSeries.vote_average)" :key="i" class="fas fa-star"></i>
                    </div>
                    <div class="stars">
                        <i v-for="i in emptyStars(stars(propSeries.vote_average))" :key="i" class="far fa-star"></i>
                    </div>
                </div>
            </div>
            <div class="d-flex justify-content-between">
                <h3>Language:</h3>
                <img class="flag" v-if="propSeries.original_language== 'en'" src="../assets/en-flag.jpg" alt="propSeries.original_language">
                <img class="flag" v-else-if="propSeries.original_language == 'it'" src="../assets/ita-flag.jpg" alt="propSeries.original_language">
                <h5 v-else>{{propSeries.original_language}}</h5>
            </div>
            <div class="hide">
                <h5>Overview: {{propSeries.overview}}</h5>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Cards',
    props: ["propSeries"],
    data() {
        return {
            urlBase: 'https://image.tmdb.org/t/p/w342'
        }
    },
    methods: {
        stars(vote) {
            return Math.ceil(vote / 2);
        },
        emptyStars(stellePiene) {
            let totStars = 5;
            return totStars - stellePiene;
        }
    }
}
</script>

<style lang='scss' scoped>
@import '../style/variables.scss';
@import '../style/general.scss';

.description{
    color: white;
    background-color: $main-color;
    padding: 25px 20px;
    top: 0;
    left: 12px;
    width: calc(100% - 12px);
    height: 100%;
    display: none;
}

.beyond-poster:hover{
    display: none;
}

.beyond-poster:hover .description{
    display: block;
}

.poster{
     width: 100%;
     height: 100%;
     object-fit: cover;
}

.flag{
    width: 30px;
    height: 18px;
    border-radius: 12px;
}

.stars{
    display: inline-block;
}

h1{
    font-size: 1.6rem;
    font-weight: bold;
}

h3{
    font-size: 1rem;
    font-weight: bold;
}

h5{
    font-size: 0.8rem;
}

.hide{
    width: 100%;
    height: 35%;
    overflow: auto;
}


</style>