<template>
    <main>
        <h1 class="text-center mb-5 pt-3 index-title">Film</h1>
        <div class="container">
            <div class="row">
                <Card v-for="movie in propFindMovies" :key="movie.id" :propMovie='movie'/>
            </div>
        </div>
        <h1 class="text-center mb-5 mt-3 index-title">Series</h1>
        <div class="container">
            <div class="row">
                <CardSeries v-for="tvShow in tvSeries" :key="tvShow.id" :propSeries='tvShow'/>
            </div>
        </div>
    </main>
</template>

<script>
import Card from './Card.vue';
import CardSeries from './CardSeries.vue';

export default {
    name: 'Main',
    components: {
        Card,
        CardSeries
    },
    props: {
        "propFindMovies" : Array,
        "tvSeries" : Array
    }

}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

main{
    background-color: $secondary-color;
    min-width: 450px;
}

.index-title{
    text-transform: uppercase;
    color: red;
}

</style>