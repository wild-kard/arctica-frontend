<template>
<div class="page">
<header>
<h1>Package 7 is now complete.</h1>
 <h2>Please remove DVD 7 and SD card 7.</h2>
 <h2>Place SD card 7, and backups CD 7 and DVD 7 into Envelope 7.</h2> 
 <h2>This envelope should be stored somewhere...[placeholder text]</h2>
 </header>
      <div class="form_container">
        <form>
            <div class="lg_checkbox_container">
                <input type="checkbox" v-model="checkbox" name="checkbox">
                <label for="checkbox">My #7 devices have been placed into Envelope 7.</label>
            </div>
        </form>
        <div class="btn_container"> 
            <button v-if="checkbox" @click="acknowledge()" class="btn">Proceed</Button>
            <button v-else @click="warn()" class="btn3">Proceed</Button>
        </div>
    </div> 

</div>

</template>

<script>
export default {
  name: 'Setup49a',
  components: {
    },
    methods: {
        acknowledge(){
            console.log('user ack, package 7 completed')
            this.$router.push({ name: 'Setup49b' })
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
