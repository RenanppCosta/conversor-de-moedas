<template>
    <div class="container">
    <div class="card" v-for="(coin, key) in coins" :key="key">
        <div class="card-header">
            <div class="card-title h3">{{coin.name}}</div>
            <div class="card-subtitle text-gray">{{key}}</div>
        </div>
        <div class="card-body">
            <label for="value">O valor da {{coin.name}} é : </label>
            <input type="number" class="value" name="value" v-model="value">
            <span class="h5">{{key}} {{value * coin.high}}</span>
        </div>
    </div>
    </div>
</template>

<script>
export default{
    data(){
        return{
            value: ""
        }
    },
    props: {coins: {type: Object, required: true} }
};


</script>

<style scoped>
.container{
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
}

.card{
    width: 30%;
    margin: 1rem;
}

.card-body{
    display: flex;
    flex-direction: column;
}

input{
    width: 40%;
    margin-top: 0.3rem;
}
@media(max-width:900px){
    .card{
        width: 100%;
    }
}
</style>