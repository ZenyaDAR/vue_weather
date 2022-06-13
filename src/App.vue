<template>
  <fillter-city 
  @city="fechCity"
  />
  <weather-card 
  :tempcity="this.tempcity" 
  :namecity="this.namecity" 
  :speedwidcity="this.speedwidcity" 
  />
</template>

<script>
import FillterCity from './components/FillterCity'
import WeatherCard from './components/WeatherCard'
  export default {
    components:{FillterCity,WeatherCard},
    data(){
      return{
        tempcity:'',
        namecity:'',
        speedwidcity:'',
      }
    },
    methods: {
      fechCity(event){
        fetch(event).then(response =>response.json()).then((res) =>{
          console.log(res)
          this.tempcity = Math.round(res.main.temp);
          this.namecity = res.name;
          this.speedwidcity = res.wind.speed
        })
      },
    },
  }
</script>

<style>
body{
  margin: 0;
  padding: 10px;
}
</style>