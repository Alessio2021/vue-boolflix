.<template>
  <header>
      <input type="text" placeholder="Search" v-model="searchMovie">
      <button @click="$emit('doSearch', searchMovie)">Cerca</button>
  </header>
</template>

<script>

export default {
    name: 'Header',
    data() {
        return {
           searchMovie: '',
        }
    },
    
}
</script>
    
<style>

</style>