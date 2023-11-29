<template>
  <div class="container mt-5">
    <component :is="activeComponent" @componentInfo="changeComponent($event)"></component>
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
    changeComponent(componentName){
      console.log(componentName);
      this.activeComponent = componentName;
    }
  }

}
</script>
<style>
body{
  font-family: sans-serif;
}
</style>
