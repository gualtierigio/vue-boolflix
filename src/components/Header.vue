<template>
    <header class="d-flex justify-content-between">
        <div class="logoflix">
            <img src="https://fontmeme.com/permalink/211005/c85aebf5c523af4f9627bb85f3b65e82.png" alt="">
        </div>
        <form class="d-flex">
            <div>
                <input v-model.trim="needle" type="text" class="form-control">
            </div>
            <div>
                <button @click.prevent="$emit('movieSearch', needle)" class="btn btn-dark">Cerca</button>
            </div>
        </form>
    </header>
</template>

<script>

export default {
    name: 'Header',
    data() {
        return {
            needle: ''
        }
    },
}

// link API https://developers.themoviedb.org/3/search/search-movies
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

header{
    padding: 30px;
    height: 100px;
    background-color: $main-color;
    min-width: 450px;
}

.logoflix{
    display: flex;
    img{
        width: 200px;
        height: 70px;
        padding-bottom: 20px;
    }
}

</style>