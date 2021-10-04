<template>
  <div>
    <Header @movieSearch="searchMovie" />
    <Main :movies='findMovies'/>
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
  data() {
    return {
      findMovies: []
    }
  },
  methods: {
      searchMovie(needle) {
            if(needle > 1) {
            axios.get('https://api.themoviedb.org/3/search/movie',
                {
                params: {
                    api_key: 'e5b162d1b0fd1b8d4251ad244ce88b8f',
                    query: needle
                }
            })
            .then((resp) => {
                this.movies = [...resp.data.results];
            })}
          }
  }

};
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/variables.scss';

</style>
