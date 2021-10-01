<template>
    <header>
        <form class="d-flex">
            <div>
                <input v-model.trim="needle" type="search" class="form-control" v-on:submit.prevent>
            </div>
            <div>
                <button @click="searchMovie" class="btn btn-dark">Cerca</button>
            </div>
        </form>
    </header>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Header',
    data() {
        return {
            needle: '',
        }
    },
    methods: {

        searchMovie() {
            axios.get('https://api.themoviedb.org/3/search/movie',{
                params: {
                    api_key: 'e5b162d1b0fd1b8d4251ad244ce88b8f',
                    query: this.needle
                }
            })
            .then((resp) => {
            console.log(resp.data.results);
        }).catch(error => console.log(error))
    }

}
}
</script>

<style lang="scss" scoped>

header{
    padding: 30px;
    height: 100px;
    background-color: rgb(44, 44, 44);
}

</style>