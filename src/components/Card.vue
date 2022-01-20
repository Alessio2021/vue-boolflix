.<template>
    <li>
        <img :src="'https://image.tmdb.org/t/p/w342' + img" alt="">
        <h2>Title: {{title}}</h2>
        <h4>Original title: {{ origTitle }}</h4>
        <h5>Language: <i :class="'flag flag-' + getFlag(Language)"></i></h5>
        <i
            v-for="star in 5"
            :key="star"
            :class="(star <= numTrans(vote)) ? 'fas fa-star' : 'far fa-star'"
        />
    </li>
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

<style>

</style>