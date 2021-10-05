<template>
    <div class="col-12 col-md-4 col-lg-3 mb-4">
        <img src="" alt="">
        <div class="description">
            <div>
                <img v-if="propMovie.poster_path" class="img-fluid poster" :src="urlBase+propMovie.poster_path" alt="Movie poster">
                <img v-else  class="img-fluid poster" src="https://via.placeholder.com/342x458" alt="Movie poster">
            </div>
            <h3>{{propMovie.title}}</h3>
            <h5>{{propMovie.original_title}}</h5>
            <div class="avarange-vote mb-2">
                <div class="stars">
                    <i v-for="i in stars(propMovie.vote_average)" :key="i" class="fas fa-star"></i>
                </div>
                <div class="stars">
                    <i v-for="i in emptyStars(stars(propMovie.vote_average))" :key="i" class="far fa-star"></i>
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

h3{
    font-size: 1rem;
    font-weight: bold;
}

h5{
    font-size: 0.8rem;
}


</style>