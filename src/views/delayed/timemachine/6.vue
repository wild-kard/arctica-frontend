<!-- This page will be a popup that appears everytime the user logs in, when the user has reecived a notice from a Time Machine Operator but has not yet presented Arctica with the
Time Machine Key obtained from the meeting.-->

<template>
<div class="page">
    <header>
        <h1>Once you've received your Time Machine Key...</h1>
        <h2>Please insert the SD card you were given and reboot this machine</h2>
    </header>
    

        <div class="btn_container"> 
            <button @click="acknowledge()" class="btn">Ok</Button>
        </div>



</div>

</template>

<script>

export default {
  name: 'TimeMachine6',
  components: {
    },
    methods: {
        acknowledge(){
            console.log('user ack, closing popup')
            this.$router.push({ name: 'dashboard' })
        },

    },
}
</script>
