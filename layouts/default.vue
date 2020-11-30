<template>
  <div class="container">
    <Header />
    <Nuxt />
  </div>
</template>

<script>
import Header from '../components/Header'
export default {
  components:{
    Header
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-size: 1rem;
  background-color: #f4f4f4;
  line-height: 1.6;
}

a{
  color:#666;
}

ul{
  list-style: none;
}

.container{
  max-width: 800px;
  margin: 2rem auto;
  background-color: #fff;
  padding: 2rem auto;
  overflow: hidden;
}
</style>
