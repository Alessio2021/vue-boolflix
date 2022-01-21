.<template>
    <div class="bg-secondary">
        <img v-if="img" :src="'https://image.tmdb.org/t/p/w342' + img" alt="">
        <img v-else :src="'https://www.google.com/url?sa=i&url=https%3A%2F%2Fcommons.wikimedia.org%2Fwiki%2FFile%3ANo-Image-Placeholder.svg&psig=AOvVaw2qOAVnGczIMkg-X59Vqu64&ust=1642845720618000&source=images&cd=vfe&ved=0CAsQjRxqFwoTCLjcmrTLwvUCFQAAAAAdAAAAABAn'" alt="">
        <h2>Title: {{title}}</h2>
        <h4>Original title: {{ origTitle }}</h4>
        <h5>Language: <i :class="'flag flag-' + getFlag(Language)"></i></h5>
        <i
            v-for="star in 5"
            :key="star"
            :class="(star <= numTrans(vote)) ? 'fas fa-star' : 'far fa-star'"
        />
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: ['img', 'title', 'origTitle', 'Language', 'vote', ],
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

<style lang="scss">
    section {
        padding: 1em;
    }
</style>