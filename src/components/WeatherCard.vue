<template>
<div class="card">
    <div class="none" v-if="this.namecity.length < 1">Выберите город</div>
    <div v-else class="content">
        <div class="name"><h1>{{namecity}}</h1></div>
        <div class="temp"><h2>{{tempcity}}*C</h2></div>
        <div class="speed"><h2>{{speedwidcity}} m/s</h2></div>
    </div>
</div>
</template>

<script>
    export default {
        name:'weather-cart',
        data() {
            return {
                
            }
        },
        props:{
            tempcity:{
                type:Number,
                require: true
            },
            namecity:{
                type:String,
                require: true
            },
            speedwidcity:{
                type:Number,
                require: true
            }
        }
    }
</script>

<style scoped>
.card{
    max-width: 350px;
    min-width: 250px;
    min-height: 300px;
    max-height: 350px;
    background: orangered;
    margin: 0 auto;
    margin-top: 70px;
    padding: 10px;
    border-radius: 10px;
    text-align: center;
    font-family: Inter;
    color: white;
}
.name{
    font-size: 20px;
}
.temp,.speed{
    font-size: 30px;
    color: white;
}
.temp h2{
    text-shadow: 0 0 4px;
}
.none{
    color: yellow;
    font-size: 30px;
    margin-top: calc(50% - 40px);
}


</style>