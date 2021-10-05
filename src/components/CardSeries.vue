<template>
    <div class="col-12 col-md-4 col-lg-3 mb-4">
        <div class="description">
            <div>
                <img v-if="propSeries.poster_path" class="img-fluid poster" :src="urlBase+propSeries.poster_path" alt="Soap poster">
                <img v-else  class="img-fluid poster" src="https://via.placeholder.com/342x458" alt="Series poster">
            </div>
            <h3>{{propSeries.name}}</h3>
            <h5>{{propSeries.original_name}}</h5>
            <div class="avarange-vote mb-2">
                <div class="stars">
                    <i v-for="i in stars(propSeries.vote_average)" :key="i" class="fas fa-star"></i>
                </div>
                <div class="stars">
                    <i v-for="i in emptyStars(stars(propSeries.vote_average))" :key="i" class="far fa-star"></i>
                </div>
            </div>

            <img class="flag" v-if="propSeries.original_language== 'en'" src="../assets/en-flag.jpg" alt="propSeries.original_language">
            <img class="flag" v-else-if="propSeries.original_language == 'it'" src="../assets/ita-flag.jpg" alt="propSeries.original_language">
            <h5 v-else>{{propSeries.original_language}}</h5>
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