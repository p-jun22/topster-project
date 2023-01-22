<template>
  <div class="container">
    
      <ImageBoard></ImageBoard>
  </div>
</template>

<script>
import ImageBoard from './ImageBoard.vue';

export default {
  name: 'MenuTap',
  components: {
    ImageBoard 
  },
  data() {
    return {
      array: ['Download', 'Upload', 'Back Up', 'Nickname', 'Pstr/Cvr Slct', 'Delete'],
      inputText: ''
    }
  },
  methods: {
    updateInput(input) {
      this.inputText = input
    },

  }
}

</script>

<style scoped>
.container {
  margin: 0;
  position: absolute;
  width: 18%;
  height: 75%;
  background: #404040;
  position: relative;
  display: flex;
  flex-direction: column;
  text-align: center;
  border-radius: 0 0 4vh 0;
}

.titlebar {
  margin-top: 2%;
  margin-bottom: 2%;
  height: 5%;
  display: flex;
  justify-content: flex-end;
}

.logo {
  width: 1%;
  height: 1%;
}

.logo>img {
  max-width: 100%;
}

.title {
  font-size: 100%;
  font-weight: 700;
  font-family: 'Inter';
  color: #169A00;
}

.inline-flex {
  display: inline-flex;
  margin-bottom: 1vh;
  justify-content: space-evenly;
  font-size: 1vh;
}


</style>