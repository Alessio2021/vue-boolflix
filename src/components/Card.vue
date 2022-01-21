.<template>
    <div class="bg-secondary my_li">
        <div class="card my_card">
            <img v-if="img" :src="'https://image.tmdb.org/t/p/w342' + img" alt="">
            <img v-else src="https://cdn.download.it/ms/static/images/poster-placeholder.png" alt="">
        </div>
        <div class="info">
            <h3 class="text-light">Title: {{title}}</h3>
            <h5 class="text-light">Original title: {{ origTitle }}</h5>
            <h5 class="text-light">Language: <i :class="'flag flag-' + getFlag(Language)"></i></h5>
            <h5 class="stars">
                <span class="text-light">Voto: </span> <i
                v-for="star in 5"
                :key="star"
                :class="(star <= numTrans(vote)) ? 'fas fa-star' : 'far fa-star'"
                />
            </h5>
            <h5 class="text-light">Overview: {{ overview }}</h5>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: ['img', 'title', 'origTitle', 'Language', 'vote', 'overview'],
    data() {
        return {
            
        }
    },methods: {
        getFlag(value) {
            switch (value) {
                default:
                    value
                break;
                    
                case 'en':
                    value = 'us'
                    break;
                    
                case 'ja':
                    value = 'jp'
                    break;
                    
                case 'ur':
                    value = 'pk'
                    break;
                    
                case 'ko':
                    value = 'kr'
                    break;
                    
            }
            return value
        },
        numTrans(num) {
            const numberStar = parseFloat(num)
            return Math.round(numberStar / 2);
        }
    },
}
</script>

<style lang="scss" scoped>
    .my_li {
        margin: 1em;
        width: 300px;
        transition: 2s;
        position: relative;

        .my_card{
            border: 1px solid black;
            border-radius: 20px;
            overflow: hidden;

            img {
                width: 100%;
            }
        }

        .info {
            display: none;
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            border-radius: 20px;
            padding: 2em 1.5em 0 1.5em;
            overflow: auto;
            svg {
                color: yellow;
            }
        }
    }
    .my_li:hover {
        cursor: pointer;

        .info {
            display: block;
            border: 1px solid black;
        }
        .my_card {
            opacity: 0.1;
        }
    } 
</style>

<!--       _
       .__(.)< (MEOW)
        \___)   
 ~~~~~~~~~~~~~~~~~~-->