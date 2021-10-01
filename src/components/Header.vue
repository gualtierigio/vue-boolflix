<template>
    <header>
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

header{
    padding: 30px;
    height: 100px;
    background-color: rgb(44, 44, 44);
}

</style>