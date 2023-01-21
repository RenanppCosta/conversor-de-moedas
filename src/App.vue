<template>
  <div class="container grid p-2">
    <div class="card p-2">
      <h1 class="h1">Conversor de Moedas</h1>
    </div>
    <Coins :coins="coins"/>
  </div>
</template>

<script>
import { onMounted, reactive, toRefs } from "vue"
import api from "./services/api"
import Coins from "./components/Coins.vue"

export default {
  name: "App",
  components: {Coins},
  setup(){

    const data = reactive({
      coins: {}
    });

    onMounted(async ()=>{
      const res = await api.all();

      data.coins = res.data
    })

    return { ...toRefs(data) }
  }
}
</script>


<style scoped>

</style>
