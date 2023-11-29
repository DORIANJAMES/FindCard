<template>
  <div class="container mt-5">
    <component :is="activeComponent" @componentInfo="componentInfo"></component>
    {{activeComponent}}
  </div>
</template>
<script>
import GameCards from "./components/GameCards.vue";
import Failure from "./components/Failure.vue";
import Celebrate from "./components/Celebrate.vue";

export default {
  name:"App",
  components:{GameCards,Failure,Celebrate},
  data(){
    return{
      activeComponent:'GameCards',
    }
  },
  methods:{
    componentInfo(data){
      if(data){
        this.activeComponent = "Celebrate";
      }else{
        this.activeComponent = "Failure";
      }
    }
  },

}
</script>
<style>
body{
  font-family: sans-serif;
}

.component-change{

}
</style>
