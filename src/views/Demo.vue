<template>
    <div>
        <h2>Demo Data</h2>
        <button v-on:click="count++">Count = {{ count }}</button>
        <br>
        <h2>Demo Method </h2>
        <button v-on:click="demomethod('method')">Say hello method</button>
        <br>
        <h2>Demo Computed</h2>
        <p>Original message: "{{ message }}"</p>
        <p>Computed reversed message: "{{ reversedMessage }}"</p>
        <h2>Demo watched</h2>
        <br>
        <h2>Demo Props</h2>


    </div>
</template>

<script>

    export default {
        name: "Demo",
        data(){
            return {
                count: 0,
                message:'Strong'
            }
        },
        methods:{
            demomethod(event) {
                alert('Hello  ' + event)

            }
        },
        computed:{
            reversedMessage: function () {
                return this.message.split('').reverse().join('')
            }
        },

    }


</script>

<style scoped>

</style>