<template>
  <div class="container">
    <h2>Welcome to Dad Joke</h2>
  </div>
</template>

<script>
export default {
  head(){
    return{
      title:'Home',
      meta:[
        {
          hid:'description',
          name:'description',
          content:'this example dad joke'
        }
      ]
    }
  }
}
</script>
<style scoped>
 h2{
   margin: 0 20px;
 }
</style>
