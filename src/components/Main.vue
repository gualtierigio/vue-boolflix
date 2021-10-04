<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col-6 col-md-4 col-lg-2">
                    <Cards v-for="movie in propFindMovies" :key="movie.id" :propMovie='movie'/>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import Cards from './Cards.vue';

export default {
    name: 'Main',
    components: {
        Cards
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