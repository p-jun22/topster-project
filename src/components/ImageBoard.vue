<template>
  <div class="imageBoard">
    <SearchBar></SearchBar>
    <div class="container" v-for="i in 10" :key="i">
      <ImageItem v-for ="ImageItem in 2" :key="ImageItem"></ImageItem>
    </div>
  </div>
</template>

<script>
import ImageItem from './ImageItem.vue'
import SearchBar from './SearchBar.vue'
export default {
    name: 'ImageBoard' ,
    components: {
      ImageItem, SearchBar
    }
}
</script>

<style scoped>
.imageBoard{
  width: 90%;
  height: inherit;
  background: #646464;
  box-shadow: 0 1% 1% rgba(0, 0, 0, 0.25);
  border-radius: 0.5vh;
  overflow-y: scroll;
  align-self: center;
  align-content: center;
} 
.container{
  display: flex;
  align-self: center;
}


.imageBoard::-webkit-scrollbar{
  width: 1vh;
  border-radius: 1vh;
}

.imageBoard::-webkit-scrollbar-thumb {
  height: 10%;
  /* 스크롤바의 길이 */
  background: #00000060;
  /* 스크롤바의 색상 */

  border-radius: 1vh;
}
.imageBoard::-webkit-scrollbar-track{
  background: #2f3831;
  /*스크롤바 뒷 배경 색상*/
  border-radius: 1vh;
}


</style>