<template>
  <div>
    <nux-link to="/">Back Home</nux-link>
    <h1>{{joke}}</h1>
    <hr>
    <p>Joke ID : {{$route.params.id}}</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data:() =>{
    return{
      joke:{}
    }
  },
 async created(){
     const config = {
      headers:{
        'Accept':'application/json'
      }
    }
   
   try {
    const response = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
    // console.log(response.data)
    this.joke = response.data.joke;
    console.log(this.joke)
   } catch (error) {
     console.log(error)
   }
  },
  head(){
    return{
      title: this.joke,
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

</style>