<script>
import Card from "./Card.vue";
import DefaultCard from "./DefaultCard.vue"

export default {
  name: 'GameCards',
  components: {Card, DefaultCard}
}
</script>

<template>
  <div class="row">
    <div class="col-md-13 col-md-offset-3">

      <div class="game-area">
        <h1 class="title">DUMAN <span>Nerede</span> <strong>?</strong></h1>
        <h4 class="description">Açık arktlardan birini seçtikten sonra, kapalı olan karta tıklayınız.</h4>
        <div class="container">
          <Card v-for="card in 5"></Card>
        </div>
        <div class="container">
          <DefaultCard></DefaultCard>
        </div>
      </div>


    </div>
  </div>
</template>

<style scoped>

.title {
  text-align: center;
  color: rosybrown;
}

.title span {
  color: mediumpurple;
}

.title strong {
  color: darkred;
}

.description {
  color: grey;
  text-align: center;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;

}

</style>
