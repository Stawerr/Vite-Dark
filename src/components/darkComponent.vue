<template>
   <button @click="submit">Toggle dark mode</button>
</template>

<script>
    export default {
        data(){
            return{
                
            }
        },
        created() {
            
        },
        methods: {
            submit(){
                document.body.classList.toggle('light');
            }
        },
    }
</script>

<style>

</style>