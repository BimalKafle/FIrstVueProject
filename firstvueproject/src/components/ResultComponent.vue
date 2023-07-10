<template>
  <div class="Result">
    {{Score}}
    <p class="ranks" >{{ranks}}</p>
    
  </div>
</template>

<script>
export default {
props:['Score'],
data(){
    return{
        ranks:null
        }
    },
mounted(){
     if(this.Score<2500){
        this.ranks="Samurai finger";
     }
     else if(this.Score<4500){
        this.ranks="Rapid Flexes";
     }else if(this.Score<6500){
        this.ranks="Not so bad";
     }else{
        this.ranks="snail pace";
     }
    }   
}
</script>

<style>

</style>