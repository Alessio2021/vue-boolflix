.<template>
  <header>
      <input @keyup.enter="getFilm" type="text" placeholder="Search" v-model="inputSearch">
      <button @click="getFilm">Cerca</button>
  </header>
</template>

<script>
import axios from 'axios';

export default { 
    name: 'Header',
    data() {
        return {
            inputSearch: '',
            movies: null,
            inputFixed: null,
            api_key: '401d2b8a5e51bdf6caf8b6e192d59d74',
            apiStatic: 'https://api.themoviedb.org/3/search/',
            language: 'en-US',       
        }
    },
    methods: {
        getFilm() {
            const endpoint = 'movie';
            const parameters = {
                api_key: this.api_key,
                language: this.language,
                query: this.inputSearch,
            };
            this.inputFixed = this.inputSearch.replace(/ /g,"+");
            axios.get(`${this.apiStatic}${endpoint}`, { params: parameters })
            .then((result) => {
                this.movies = result.data.results
                this.$emit('doSearch', this.movies)
            })
            .catch((error) => {
                console.log(error);
            });
        },
    }
    
}
</script>
    
<style>

</style>