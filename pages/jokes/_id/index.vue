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
  // state
  data:() =>{
    return{
      joke:{}
    }
  },
  // lifeceycle component vue
 async created(){
     const config = {
      headers:{
        'Accept':'application/json'
      }
    }
   
   try {
    //  get detail joke
    const response = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
    // console.log(response.data)
    this.joke = response.data.joke; // put the response to state joke
    console.log(this.joke)
   } catch (error) {
     console.log(error)
   }
  },
  // insrt dynamic mata tag & head content for html
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