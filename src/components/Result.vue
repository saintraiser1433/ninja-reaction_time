<template>
    <p>Your reaction time is {{ reactionTime }}</p>
    <h4>{{ rank }}</h4>
</template>
   

<script>
export default {
    name: 'ResultS',
    props: ['reactionTime'],
    data() {
        return {
            rank: null
        }
     },
     mounted(){
        if(this.reactionTime < 250){
            this.rank = 'Ninja Fingers'
        }else if(this.reactionTime < 400){
            this.rank = 'Rapid Reflexes'
        }else{
            this.rank = 'Snail pace';
        }
     }

}
</script>

<style scoped></style>