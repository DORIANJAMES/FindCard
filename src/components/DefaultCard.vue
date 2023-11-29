<script>
export default{
  name:"DefaultCard",
  props:['card'],
}
</script>

<template>
  <div class="card"></div>
</template>

<style scoped>
.card{
  width: 200px;
  height: 232px;
  border-radius: 5px;
  border: 1px solid #666;
  background-color: purple;
  margin-left: 10px;
  background-image: url("../assets/vue-js-egitim-background.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  box-shadow:0px 9px 55px #666;
}
.card:hover{
  box-shadow: 0px 5px 30px #666;
  transition: box-shadow .5s;
}
.card img{
  width: 100%;
  height: 100%;
}
</style>
