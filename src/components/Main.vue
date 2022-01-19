.<template>
  <main>
      <ul>
          <li>
              <img src="" alt="">
              <h2>Titolo</h2>
              <h2>Titolo originale</h2>
              <h2>Lingua</h2>
              <h2>Voto</h2>
          </li>
      </ul>
  </main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    props: {
        searchMovieMain: {
            type: String,
        }
    },
    data() {
        return {
            movies: null
        }
    },
    computed: {
        getAxios() {
            axios.get(this.searchMovieMain)
            .then((result) => {
                this.movies = result.data.results
            })
            .catch((error) => {
                console.log(error);
            });
            return this.movies
        },
    },
    methods: {
        // getAxios() {
        //     axios.get(this.searchMovieMain)
        //     .then((result) => {
        //         this.movies = result.data.results
        //     })
        //     .catch((error) => {
        //         console.log(error);
        //     });
        // },
    }
}
</script>

<style>

</style>