<template>
  <div id="app">
    <div class="main">
      <MenuTap>
      </MenuTap> 
      <PosterList></PosterList> 
      <PosterReview></PosterReview>
      <DeleteButton></DeleteButton>
    </div>
  </div>
</template>

<script>
import MenuTap from './components/MenuTap.vue';
import PosterList from './components/PosterList.vue';
import PosterReview from './components/PosterReview.vue';
import DeleteButton from './components/DeleteButton.vue';

const HOST    = 'https://ws.audioscrobbler.com/2.0/?'

export default {
  name: 'App',
  created(){
    this.$http.get('api/movies')
      .then((res) => {
        this.movies = res.data
        console.log(this.movies[0])
      })
  },
  data(){
    return{
      movies: [],
      result: '',
      buttons: [
        'Download', 
        'Upload', 
        'Back Up', 
        'NickName', 
        'Pstr/Cvr Slct', 
        'Delete'
      ]
    }
  },
  components: {
    MenuTap, PosterList, PosterReview, DeleteButton
  },
  methods:{
    loadApiData(){
      this.$axios
        .get(HOST, {
          params: {
            method      : 'album.search',
            album       : 'aimer',
            api_key     : process.env.VUE_APP_LASTFM_API_KEY,
            format : 'json'
          }
        }).then((res) => {
          console.log(res.data)
          this.result = res.data['results']['albummatches']['album'][0]['image'][3]['#text']
        }).catch((error) => {
          console.error(error)
        }).finally(() => {
          console.log('API 호출 끝')
        })
    }
  }
}
</script>

<style scoped>

.main{
  background-color: #202020;
  height: 100%;
  width: 100%;
  display: flex;
  position: absolute;
  margin: 0;
}
</style>