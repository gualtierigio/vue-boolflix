<template>
  <div>
    <Header @movieSearch="searchMovie" />
    <Main :propFindMovies='findMovies' :tvSeries='findSeries'/>
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
      apiMoviesUrl: 'https://api.themoviedb.org/3/search/movie',
      apiSeriesUrl: 'https://api.themoviedb.org/3/search/tv',
      findMovies: [],
      findSeries: []
    }
  },
  methods: {
      searchMovie(needle) {
            if(needle.length > 1) {
            axios.get(this.apiMoviesUrl,
                {
                params: {
                    api_key: 'e5b162d1b0fd1b8d4251ad244ce88b8f',
                    query: needle
                }
            })
            .then((resp) => {
                this.findMovies = [...resp.data.results];
            })};
            axios.get(this.apiSeriesUrl,
                {
                params: {
                    api_key: 'e5b162d1b0fd1b8d4251ad244ce88b8f',
                    query: needle
                }
            })
            .then((resp) => {
                this.findSeries = [...resp.data.results];
            })
          }
  }

};
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/variables.scss';

</style>
