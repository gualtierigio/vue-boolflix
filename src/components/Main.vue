<template>
    <main>
        <h1 class="text-center">Film</h1>
        <div class="container">
            <div class="row">
                <Card v-for="movie in propFindMovies" :key="movie.id" :propMovie='movie'/>
            </div>
        </div>
        <h1 class="text-center">Series</h1>
        <div class="container">
            <div class="row">
                <Card v-for="tvShow in tvSeries" :key="tvShow.id" :propSeries='tvShow'/>
            </div>
        </div>
    </main>
</template>

<script>
import Card from './Card.vue';

export default {
    name: 'Main',
    components: {
        Card
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
}

</style>