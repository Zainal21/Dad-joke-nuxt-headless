<template>
  <div>
    <JokeList v-for="joke in jokes" 
    :key="joke.id" 
    :id="joke.id" 
    :joke="joke.joke" />
  </div>
</template>

<script>
import JokeList from '../../components/JokeList'
import axios from 'axios'
export default {
   data:()=>{
    return{
      jokes:[
        {
          id : 1,
          joke:'test'
        }
      ]
    }
  },
  components:{
    JokeList
  },
  async created(){
    const config = {
      headers:{
        'Accept':'application/json'
      }
    }
   
   try {
    const response = await axios.get('https://icanhazdadjoke.com/search', config)
    // console.log(response.data)
    this.jokes = response.data.results
   } catch (error) {
     console.log(error)
   }
  },
  head(){
    return{
      title:'Dad Joke',
      meta:[
        {
          hid:'description',
          name:'description',
          content:'this example for dark joke list'
        }
      ]
    }
  }
}
</script>