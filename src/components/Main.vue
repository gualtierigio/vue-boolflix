<template>
    <main>
        <div class="container">
            <div class="row">
                <Card v-for="movie in propFindMovies" :key="movie.id" :propMovie='movie'/>
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
    }

}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

main{
    background-color: $secondary-color;
}

</style>