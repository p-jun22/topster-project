<template>
    <div class="search-section">
    <!-- 검색바 섹션 -->
    <!-- TODO -->
    <!-- 검색바 안에 검색 버튼 넣기 -->
    <!-- 검색바 코너 라운드 넣기 -->
    <!-- 검색바 디자인 -->
    <div class="search-bar">
      <!-- 검색 기능 만들어야함 -->
      <BaseInput class="search-input" :input="inputText" @update-input="updateInput" />
    </div>
  </div>
</template>

<script>
import BaseInput from './BaseInput.vue';
export default{
  name: 'SearchBar',
  components:{
    BaseInput
  }
}
</script>

<style scoped>
*{
  margin: 0;
  border: 0;
  padding: 0;
}
.search-section{
  position: sticky;
  top: 0%;
  margin: 0;
  height: 5vh;
  display: flex;
  justify-content: center;
  background-color: #646464;
}

.search-bar {
  overflow: inherit;
  width: 80%;
}

.search-input {
  width: 100%;
  height: 100%;
}
</style>


