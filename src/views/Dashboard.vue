<template>
  <Compromised v-if="this.tripwire == false" />
  <div v-else class="page">
    <Nav />
      <div class="dashboard">
        <div class="head_container">
          <h1>Wallets</h1>
        </div>
        <router-link class="wallet_container" :to="{ name: 'hot' }">
            <div class="wallet_container_left">
            <h2>Hot Wallet</h2>
            <h2 class="time_decay">Spend Now</h2>
            </div>
            <div class="wallet_container_right">
              <h2 class="balance_overview">{{ this.hotBalance }} BTC</h2>
              <span class="carat"><img src="@/assets/carat_right.png"/></span>
            </div>
        </router-link> 

        <router-link class="wallet_container" :to="{ name: 'immediate' }">
            <div class="wallet_container_left">
            <h2>Immediate Wallet</h2>
            <h2 class="time_decay">2 SD cards</h2>
            </div>
            <div class="wallet_container_right">
              <h2 class="balance_overview">{{ this.immediateBalance }} BTC</h2>
              <span class="carat"><img src="@/assets/carat_right.png"/></span>
            </div>
        </router-link> 

        <router-link class="wallet_container" :to="{ name: 'delayed' }">
          <div class="wallet_container_left">
          <h2>Delayed Wallet</h2>
          <h2 class="time_decay">5 SD cards + 2 Time Machine Keys</h2>
          </div>
          <div class="wallet_container_right">
            <h2 class="balance_overview">{{ this.delayedBalance }} BTC</h2>
            <span class="carat"><img src="@/assets/carat_right.png"/></span>
          </div>
        </router-link> 
          <div class="decay_timer">
            <h2 class="time_decay">Approximate time until next decay: 1 year & 162 days</h2>
          </div>
      </div>
  </div>
</template>


<script>
import Nav from '@/components/Nav'
import { RouterView, RouterLink } from "vue-router";
import store from '../store.js'
import Compromised from './tripwire/compromised.vue'
{
  RouterView;
  RouterLink
}

export default {
  name: 'Dashboard',
  components: {
    Nav,
    Compromised
  },
     mounted(){
      this.hotBalance = store.getters.getHotBalance
      this.immediateBalance = store.getters.getImmediateBalance
      this.delayedBalance = store.getters.getDelayedBalance
 },
 data(){
  return{
    hotBalance: store.getters.getHotBalance,
    immediateBalance: store.getters.getImmediateBalance,
    delayedBalance: store.getters.getDelayedBalance,
  }
 },
 computed:{
  tripwire(){
    return store.getters.getTripwireHealthy}
 },
 hotBalance(){
  return store.getters.getHotBalance
 },
 immediateBalance(){
  return store.getters.getImmediateBalane
 },
 delayedBalance(){
  return store.getters.getDelayedBalance
 }
}
</script>

<style scoped>
h2{
  color:#000000;
}
.time_decay{
  color:#777777;
}

</style>