<!-- BaseInput.vue - 싱글 파일 컴포넌트 구조-->
<template>
  <input 
  type="text" 
  :value="input"
  @input="updateInput"/>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      require: true
    }
  },
  methods: {
    updateInput(e) {
      //console.log(e.target.value)
      this.$emit('update-input', e.target.value)
    }
  } 
}
</script>