<template>
<div class="page">
    <header>
        <h1>SD Card 3</h1>
        <h2>Please power off this device, insert SD card 3 and reboot the machine.</h2>
    </header> 
        <div class="btn_container"> 
            <button @click="acknowledge()" class="btn">Ok (this will close the application)</Button>
        </div>
</div>

</template>

<script>
export default {
  name: 'Setup30',
    methods: {
        acknowledge(){
            console.log('user ack, close application')
        },
        warn(){
            console.log('user trying to proceed without checkbox validation')
        },
    },
    data(){
        return{}
    },
    }
</script>

