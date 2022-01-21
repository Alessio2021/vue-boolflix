.<template>
    <div class="card bg-secondary my_card">
        <img v-if="img" :src="'https://image.tmdb.org/t/p/w342' + img" alt="">
        <img v-else src="https://cdn.download.it/ms/static/images/poster-placeholder.png" alt="">
        <div class="info">
            <h2>Title: {{title}}</h2>
            <h4>Original title: {{ origTitle }}</h4>
            <h5>Language: <i :class="'flag flag-' + getFlag(Language)"></i></h5>
            <div class="stars">
                <i
                v-for="star in 5"
                :key="star"
                :class="(star <= numTrans(vote)) ? 'fas fa-star' : 'far fa-star'"
                />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: ['img', 'title', 'origTitle', 'Language', 'vote', 'hover'],
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
    .my_card {
        margin: 1em;
        width: 300px;
        border: 1px solid black;
        border-radius: 20px;
        overflow: hidden;
        position: relative;
        transition: 2s;
        .info {
            display: none;
        }   
    }
</style>