<template>
<div class="page">
    <header>
        <h1>Time to setup your keys...</h1>
        <h2>Label 8 CD's "CD 1" through "CD 7", and label the final one "setup".</h2> 
        <h2>Label 7 DVDs "DVD 1" through "DVD 7".</h2> 
        <h2>Label 7 SD cards "1" through "7".</h2>
        <h2>Label 7 Envelopes "1" through "7".</h2>
    </header>
    
    <div class="form_container">
        <form>
            <div class="checkbox_container">
                <input type="checkbox" v-model="checkbox" name="checkbox">
                <label for="checkbox">My devices are properly labelled</label>
            </div>
        </form>
        <div class="btn_container"> 
            <button v-if="checkbox" @click="acknowledge()" class="btn">Continue</Button>
            <button v-else @click="warn()" class="btn3">Continue</Button>
        </div>
    </div> 


</div>

</template>

<script>

export default {
  name: 'Setup3',
  components: {
    },
    methods: {
            acknowledge(){
            console.log('user ack, media devices are ready')
            this.$router.push({ name: 'Setup4' })
        },
        warn(){
            console.log('user trying to proceed without checkbox validation')
        },

    },
    data(){
        return{
            checkbox: false,
        }
    }
}
</script>
