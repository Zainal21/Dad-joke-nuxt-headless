<template>
  <nuxt-link :to="'jokes/' + id" class="link">
    <div class="joke-list">
      <p><b>{{joke}}</b></p>
    </div>
  </nuxt-link>
</template>

<style scoped>

</style>

<script>
  export default {
    name: 'JokeList',
    props: ['joke', 'id']
  }

</script>

<style scoped>
  .joke-list {
    padding: 1rem;
    border: 1px solid #ccc;
    margin: 1rem 0;
  }
  .link{
    text-decoration: none;
  }

</style>
