<template>
<div class="page">
    <header>
        <h1>SD 2 creation complete</h1>
        <h2>Please power off this machine, remove SD 2, insert SD 3, and reboot the device.</h2>
    </header> 
        <div class="btn_container"> 
            <button @click="acknowledge()" class="btn">Ok</Button> 
        </div>

</div>

</template>

<script>
import store from '../../store.js'

export default {
  name: 'Setup14',
    methods: {
        acknowledge(){
            console.log('user ack, close application')
            //eventually need to check electronic SD label and update global state here, only allow user to proceed if correct SD is inserted
            //eventually need a step here to remove the electronic label that redirected user to step 14, added in step 5
            //eventually only allow the user to proceed here if primary machine boolean is false
        },
    },
    computed:{
        currentSD(){
            return store.getters.getCurrentSD
        }
    },
    data(){
        store.commit('setSetup2', false) //eventually change this to remove virtual label
        store.commit('setSetup9', true) //eventually change this to add a virtual label
        return{}
    }
}
</script>

