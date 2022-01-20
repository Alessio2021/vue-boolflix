.<template>
  <main>
      <ul>
          <li v-for="(movie, index) in list.movies" :key="index">
              <img src="" alt="">
              <h2>Title: {{movie.title}}</h2>
              <h4>Original title: {{ movie.original_title }}</h4>
              <h5>Language: <i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i></h5>
              <h5>Vote: {{ movie.vote_average }}</h5>
          </li>
      </ul>
  </main>
</template>

<script>
export default {
    name: 'Main',
    props: ['list'],
    data() {
        return {
            
        }
    },
}
</script>

<style>

</style>