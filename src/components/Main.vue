.<template>
  <main>
      <ul>
          <li v-for="(movie, index) in searchMovieMain" :key="index">
              <img src="" alt="">
              <h2>Titolo: {{movie.title}}</h2>
              <h4>Titolo originale {{ movie.original_title }}</h4>
              <h5>Lingua <i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i></h5>
              <h5>Voto: {{ movie.vote_average }}</h5>
          </li>
      </ul>
  </main>
</template>

<script>
export default {
    name: 'Main',
    props: ['searchMovieMain'],
    data() {
        return {
            
        }
    },
}
</script>

<style>

</style>