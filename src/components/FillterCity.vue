<template>
    <select v-model="cityfech" @change="cityNum">
        <option disabled value="">Выберите город</option>
        <option value="https://api.openweathermap.org/data/2.5/weather?lat=49.9808100&lon=36.2527200&appid=e0aa12cfb6bad018b85c187e4261aac4&units=metric">Харьков</option>
        <option value="https://api.openweathermap.org/data/2.5/weather?lat=50.4337868&lon=30.5193259&appid=e0aa12cfb6bad018b85c187e4261aac4&units=metric">Киев</option>
        <option value="https://api.openweathermap.org/data/2.5/weather?lat=49.5937300&lon=34.5407300&appid=e0aa12cfb6bad018b85c187e4261aac4&units=metric">Полтава</option>
    </select>
</template>

<script>
    export default {
        name:'filter-city',
        data(){
            return{
                cityfech:'',
            }
        },
        methods: {
            cityNum(event){
               this.$emit('city', event.target.value)
            }
        },
    }
</script>

<style scoped>
select{
    width: 100%;
    border: 3px red solid;
    border-radius: 5px;
    padding: 10px;
    font-size: 17px;
    cursor: pointer;
    outline: none;
}


</style>