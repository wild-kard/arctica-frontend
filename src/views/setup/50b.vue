<template>
<div class="page">
    <header>
        <h1>Congratulations. You have successfully completed setup.</h1>
        <h2>Now we must wait for Bitcoin Core to finish it's initial sync.</h2>
        <h2>This computer should remain on and unlocked until the blockchain has finished it's sync.</h2> 
        <h2>This can take anywhere from a few hours to a few weeks depending on your internet connection.</h2>
        <h3>Progress: 56% complete.</h3>
    </header>
        <div class="btn_container"> 
            <button v-if="this.btcCoreHealthy == true" @click="acknowledge()" class="btn">Proceed</Button>
            <button v-else @click="warn()" class="btn3">Proceed</Button>
        </div>
</div>

</template>

<script>
import store from '../../store.js'

export default {
  name: 'Setup50b',
  components: {
    },
    methods: {
        acknowledge(){
            console.log('user ack, sync complete')
            this.$router.push({ name: 'Setup51' })
        },
        warn(){
            console.log('user trying to proceed without completed sync')
        },
    },
    computed:{
        btcCoreHealthy(){
            return store.getters.getBTCCoreHealthy
        }
    },
    data(){
        store.commit('setSetup15', false) //eventually change this to remove virtual label
        return{}
    }
}
</script>
