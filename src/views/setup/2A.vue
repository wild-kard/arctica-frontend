<template>
  <header>
<h1>Let's double check your password.</h1>
 <h2>Confirm the password that you created on the previous screen.</h2> 
            <div class="form_container">
                <form>
                    <label>Enter Password</label>
                   <br><input v-model="password1" type="password" required placeholder="Your secret password">
                </form>
                <div class="btn_container"> 
                    <button v-if="password1 == this.password" @click="acknowledge()" class="btn">Continue</Button>
                    <button v-else @click="warn()" class="btn3">Continue</Button>
                    <button @click="$emit('goBack')" class="btn2">New Password</button>
                </div>
                </div>
    </header>
</template>

<!-- 
this component needs a fail condition -->

<script>

export default {
  name: 'Setup2A',
  props: ['password'],
  components: {
    },
    methods: {
        acknowledge(){
            console.log('user ack, password confirmed')
            this.$router.push({ name: 'Setup3' })
        },
        warn(){
            console.log('user trying to proceed without password match, need form correction')
        },
    },
     data(){
     return{
         password1: '',
         password2: ''
     }
 }
}
</script>

<style scoped>

form{
    margin: 30px auto;
    padding:40px;
}
</style>
