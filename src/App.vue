<template>
  <div>
    <Header @movieSearch="searchMovie" />
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from 'axios';


export default {
  name: "App",
  components: {
    Header,
    Main
  },
  methods: {
      searchMovie(needle) {
            axios.get('https://api.themoviedb.org/3/search/movie',
                {
                params: {
                    api_key: 'e5b162d1b0fd1b8d4251ad244ce88b8f',
                    query: needle
                }
            })
            .then((resp) => {
                console.log(resp.data.results);
            })
        }
  }

};
</script>

<style lang="scss">
@import './style/general.scss';

</style>
