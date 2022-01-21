.<template>
    <main class="bg-secondary">
        <h2 class="p-4 m-0">Movies</h2>
        <ul class="list-group">
            <li class="border-0 bg-secondary list-group-item d-flex flex-wrap justify-content-center" 
                v-if="list.movies.length > 0">
                <Card 
                    v-for="(movie, index) in list.movies" 
                    :key="index + 'm'"
                    :img="movie.poster_path"
                    :title="movie.title"
                    :origTitle="movie.original_title"
                    :Language="movie.original_language"
                    :vote="movie.vote_average"
                    :overview="movie.overview"
                />
            </li>
            <li class="border-0 d-flex justify-content-center bg-secondary list-group-item " v-else>
                <h1>No Movies Found</h1>
            </li>
        </ul>
        <h2 class="p-4 bg-secondary m-0">Series</h2>
        <ul class="list-group">
            <li class="border-0 bg-secondary list-group-item d-flex flex-wrap justify-content-center" 
                v-if="list.series.length > 0">
                <Card 
                    v-for="(serie, index) in list.series" 
                    :key="index + 's'"
                    :img="serie.poster_path"
                    :title="serie.name"
                    :origTitle="serie.original_name"
                    :Language="serie.original_language"
                    :vote="serie.vote_average"
                    :overview="serie.overview"
                />
            </li>
            <li class="border-0 d-flex justify-content-center bg-secondary list-group-item " v-else>
                <h1>No Series Found</h1>
            </li>
        </ul>
        <!-- <h2 class="p-4">Series</h2>
        <ul class="list-group">
            <li class="border-0 bg-secondary list-group-item d-flex flex-wrap" 

            </li>
            <li v-else class="border-0 d-flex justify-content-center bg-secondary list-group-item">
                <h1>No Series Found</h1>
            </li>
        </ul> -->
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
        getHovered() {
            
        }
    },
}
</script>

<style>
    main {
        height: calc(100vh - 103px);
    }
</style>