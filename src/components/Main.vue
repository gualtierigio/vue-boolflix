<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col-6 col-md-4 col-lg-2">
                    <Cards />
                </div>
            </div>
        </div>
        <!-- <p v-for="(movie, id) in movies" :key="id"></p> -->
    </main>
</template>

<script>
import Cards from './Cards.vue'

export default {
    name: 'Main',
    components: {
        Cards
    }

}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

main{
    background-color: $secondary-color;
}

</style>