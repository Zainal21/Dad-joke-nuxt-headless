<template>
  <form @submit.prevent="handleSearch">
    <input type="text" v-model="text" placeholder="search joke" class="search">
    <button type="submit">Search Joke</button>
  </form>
</template>

<script>
export default {
  name:'SearchJoke',
  data:() => {
    return {
      text:""
    }
  },
  methods:{
    handleSearch(){
      this.$emit('search-text',this.text)
      this.text = ''
    }
  }
}
</script>

<style scoped>
  .search{
    margin:0px 10px;
  }
</style>