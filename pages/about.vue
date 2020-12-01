<template>
  <div>
      <h2>About Page</h2>
      <p>this example jsoke</p>
  </div>
</template>

<script>
export default {
  head(){
    return{
      title:'About',
      meta:[
        {
          hid:'description',
          name:'description',
          content:'this is example for about page'
        }
      ]
    }
  }
}
</script>

<style scoped>
  h2, p{
    margin: 0 20px;
  }
</style>

