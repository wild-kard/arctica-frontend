<template>
<div class="page">
    <header>
        <h1>3 of 5 Signing Successful</h1>
        <h2>Please power off this device. Switch to a secondary, offline machine and insert SD 4 & the Transfer CD and reboot.</h2>
    </header>
    

        <div class="btn_container"> 
            <button @click="acknowledge()" class="btn">Ok (This will close the application)</Button>
        </div>



</div>

</template>

<script>
import store from '../../../store.js'

export default {
  name: '3of5success',
  components: {
    },
    methods: {
        acknowledge(){
            console.log('user ack, closing application')
        },
    },
    computed:{
        currentSD(){
            return store.getters.getCurrentSD
        },
        psbtFound(){
            return store.getters.getPSBTFound
        }
    }
}
</script>

<style>

.strong{
    font-weight: 800;
}
</style>
