.<template>
  <main>
      <ul>
          <li v-for="(movie, index) in searchMovieMain" :key="index">
              <img src="" alt="">
              <h2>{{movie.title}}</h2>
              <h2>{{ movie.original_title }}</h2>
              <h2><i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i></h2>
              <h2>{{ movie.vote_average }}</h2>
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
            apiStatic: 'https://api.themoviedb.org/3/search/movie?api_key=401d2b8a5e51bdf6caf8b6e192d59d74&query='
        }
    },
}
</script>

<style>

</style>