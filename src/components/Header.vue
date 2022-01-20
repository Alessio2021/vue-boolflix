.<template>
  <header>
      <input @keyup.enter="getAxios" type="text" placeholder="Search" v-model="inputSearch">
      <button @click="getAxios">Cerca</button>
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
           
        }
    },
    methods: {
        getAxios() {
            this.inputFixed = this.inputSearch.replace(/ /g,"+");
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=401d2b8a5e51bdf6caf8b6e192d59d74',
            {
                params: {
                    query:this.inputFixed
                }
            })
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