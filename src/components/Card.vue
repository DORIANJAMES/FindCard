<script setup>

</script>

<template>
  <div class="card">
    <img src="../assets/card-1.jpg" alt="">
  </div>
</template>

<style scoped>
.card{
  width: 200px;
  height: 232px;
  border-radius: 5px;
  border: 1px solid #666;
  background-color: purple;
  transition: box-shadow .5s;
  margin-left: 15px;
}
.card:first-child{
  margin: 0px;
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
