<!-- This page will dynamically display the current number of SD cards needed to decrypt as well as a countdown to the remaining priacy key decay schedules -->
<!-- Need to add screens to this flow prompting for each SD required to decrypt, then toggle manual decrypt state variable once complete to allow hard login -->
<template>
  <div class="page">
    <header>
      <h1>Manual Recovery Initiated.</h1>
      <h2>Please insert your next available SD card.</h2>
    </header>
    <div class="btn_container"> 
        <button @click="acknowledge()" class="btn">Ok</Button>
        <button @click="help()" class="btn2">I need help</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RecoveryInitiate',
    methods: {
        acknowledge(){
            console.log('user ack, recovery initiating')
        },
        help(){
            console.log('fetching help')
        }
    },
}
</script>

