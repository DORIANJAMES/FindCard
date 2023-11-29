<script>
export default {
  name: 'Failure',
  methods: {
    newGame() {
    }
  }
}


</script>

<template>
  <div class="container">
    <h1>Maalesef Bilemediniz...!</h1>
    <button @click="newGame">Yeni Oyun</button>
  </div>
</template>

<style>
.container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: darkred;
}

.container h1 {
  color: white;
  font-size: 3rem;
}

.container button {
  width: 200px;
  height: 50px;
  padding: 10px 20px;
  border-radius: 5px;
  border: none;
  background-color: white;
  color: darkred;
  font-size: 1.5rem;
  cursor: pointer;
  transition: all .5s;
}

.container button:hover {
  background-color: lightgreen;
  color: darkred;
  transition: all .5s;
}

</style>
