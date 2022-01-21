.<template>
    <main>
        <ul>
            <li v-if="list.movies.length > 0">
                <Card 
                    v-for="(movie, index) in list.movies" 
                    :key="index + 'm'"
                    :img="movie.poster_path"
                    :title="movie.title"
                    :origTitle="movie.original_title"
                    :Language="movie.original_language"
                    :vote="movie.vote_average"
                />
            </li>
            <li v-else>
                No Movie Found
            </li>
        </ul>
        <ul>
            <li v-if="list.series.length > 0">
                <Card 
                    v-for="(serie, index) in list.series" 
                    :key="index + 's'"
                    :img="serie.poster_path"
                    :title="serie.name"
                    :origTitle="serie.original_name"
                    :Language="serie.original_language"
                    :vote="serie.vote_average"
                />
            </li>
            <li v-else>
                No Series Found
            </li>
        </ul>
        <!-- <ul>
            <Card v-for="(serie, index) in list.series" :key="index">
                <img :src="'https://image.tmdb.org/t/p/w342' + serie.poster_path" alt="">
                <h2>Title: {{serie.name}}</h2>
                <h4>Original title: {{ serie.original_name }}</h4>
                <h5>Language: <i :class="'flag flag-' + getFlag(serie.original_language)"></i></h5>
                <h5>Vote: {{ numTrans(serie.vote_average) }}</h5>
            </li>
        </ul> -->
    </main>
</template>

<script>
import Card from './Card.vue';

export default {
    name: 'Main',
    components: {
        Card,
    },
    props: ['list'],
    data() {
        return {
            
        }
    },methods: {

    },
}
</script>

<style>

</style>