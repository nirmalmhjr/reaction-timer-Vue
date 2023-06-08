<template>
    <p>Reaction time : {{ result }} ms</p>
    <h2>{{ rankResponse }}</h2>

</template>

<script>
export default {
    props : ['result'],
    data(){
        return{
            rankResponse: null
        }
    },
    mounted(){
            if(this.result < 250){
            this.rankResponse='Ninja Finger'
            } else if(this.result < 500){
            this.rankResponse = 'you have fast fingers'
            } else {
            this.rankResponse = 'Hmm... slow pace'
            }
        }
    }

</script>

<style>

</style>