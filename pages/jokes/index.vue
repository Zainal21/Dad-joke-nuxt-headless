<template>
  <div>
    <SearchJoke v-on:search-text="SearchText"/>
    <JokeList v-for="joke in jokes" 
    :key="joke.id" 
    :id="joke.id" 
    :joke="joke.joke" />
  </div>
</template>

<script>
import JokeList from '../../components/JokeList'
import SearchJoke from '../../components/SearchJoke'
import axios from 'axios'
export default {
   data:()=>{
    return{
      jokes:[
        {
          id : 1,
          joke:'test'
        },
        {
          id : 2,
          joke:'tukang kibul'
        },
        {
          id : 3,
          joke:'tukang wibu'
        },
        {
          id : 4,
          joke:'tukang wota'
        }
      ]
    }
  },
  components:{
    JokeList,SearchJoke
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
  },
  methods:{
   async SearchText(text){
        const config = {
            headers:{
              'Accept':'application/json'
            }
          }
        
        try {
          const response = await axios.get(`https://icanhazdadjoke.com/search?trim=${text}`, config)
          // console.log(response.data)
          this.jokes = response.data.results
        } catch (error) {
          console.log(error)
        }
    }
  }
}
</script>