<template>
  <div class="container mt-5">
    <transition-group name="slideContainer" mode="out-in">
      <component key="mainComponent" :is="activeComponent" @componentInfo="changeComponent($event)"></component>
      <canvas v-show="activeComponent=='Celebrate'" id="canvas" key="canvas"></canvas>
    </transition-group>
  </div>
</template>
<script>
import GameCards from "./components/GameCards.vue";
import Failure from "./components/Failure.vue";
import Celebrate from "./components/Celebrate.vue";

export default {
  name: "App",
  components: {GameCards, Failure, Celebrate},
  data() {
    return {
      activeComponent: 'GameCards',
    }
  },
  methods: {
    changeComponent(componentName) {
      console.log(componentName);
      this.activeComponent = componentName;
    }
  }
}
</script>
<style>
body {
  font-family: sans-serif;
}

.slideContainer-enter{}
.slideContainer-enter-active{
  animation: slideIn .3s ease-in-out forwards;
}
.slideContainer-leave{}
.slideContainer-leave-active{
  animation: slideOut .3s ease-in-out backwards;
}
@keyframes slideIn {
  from {
    transform: translateX(-1000px);
    opacity: 0;
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}

@keyframes slideOut {
  from {
    transform: translateX(0px);
    opacity: 1;
  }
  to {
    transform: translateX(1000px);
    opacity: 0;
  }
}
</style>
