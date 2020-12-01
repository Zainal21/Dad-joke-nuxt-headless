<template>
  <header class="header">
    <h2 class="title">Dad Jokes</h2>
    <ul>
      <li>
        <nuxt-link to='/'>Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to='/jokes'>Jokes</nuxt-link>
      </li>
      <li>
        <nuxt-link to='/about'>About</nuxt-link>
      </li>
    </ul>
  </header>  
</template>

<script>
export default {
  name:'Header'
}
</script>

<style scoped>
  .header{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-bottom:2rem ;
    margin-bottom:1rem;
    border-bottom: 1px dotted #ccc;

  }
  .header h2{
    margin: 0 20px;
  }
  .header .title{
    font-size: 3rem;
    color:rgb(49, 47, 47);
    }
  .header ul{
    display: flex;
  }
  .header a {
    display: inline-block;
    color: white;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
    background-color: #333;
  }
</style>