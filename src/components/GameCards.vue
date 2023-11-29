<script>
import Card from "./Card.vue";
import DefaultCard from "./DefaultCard.vue"

export default {
  name: 'GameCards',
  components: {Card, DefaultCard},
  data() {
    return {
      selectedCard: null,
      answer: {},
      activeCard: "DefaultCard",
      cards: [
        {id: 1, component: "Card", image: "/src/assets/card-1.jpg"},
        {id: 2, component: "Card", image: "/src/assets/card-2.jpg"},
        {id: 3, component: "Card", image: "/src/assets/card-3.jpg"},
        {id: 4, component: "Card", image: "/src/assets/card-4.jpg"},
        {id: 5, component: "Card", image: "/src/assets/card-5.jpg"},
      ]
    }
  },
  created() {
    let answer = Math.ceil(Math.random() * this.cards.length);
    this.answer = this.cards[answer - 1];
  },
  methods: {
    showCard(card) {

      if (this.selectedCard != null) {
        this.activeCard = card.component;

        setTimeout(() => {
          if (this.selectedCard === this.answer.id) {
            this.$emit("componentInfo", 'Celebrate');
          } else {
            this.$emit("componentInfo", 'Failure');
          }
        }, 2000);

      } else {
        alert("Lütfen bir kart seçiniz.");
      }
    }
  }
}
</script>

<template>
  <div class="row">
    <div class="col-md-13 col-md-offset-3">

      <div class="game-area">
        <h1 class="title">DUMAN <span>Nerede</span> <strong>?</strong></h1>
        <h4 class="description">Açık arktlardan birini seçtikten sonra, kapalı olan karta tıklayınız.</h4>
        <div class="container">
          <transition-group name="rotate-all" appear class="card-container">
            <Card
                :class="{shadow: selectedCard === card.id}"
                @click.native="selectedCard = card.id"
                v-for="(card) in cards"
                :cardImage="card"
                :key="card.id">
            </Card>
          </transition-group>
        </div>
        <div class="container">
          <transition name="rotate" mode="out-in">
            <component :is="activeCard" @click.native="showCard(answer)" :cardImage="answer"></component>
          </transition>
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

.container, .card-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
}

.shadow {
  box-shadow: 0px 5px 48px #30969f !important;
  transition: box-shadow .5s;
}

/************************** Açık kartların animasyonları için gerekli olan trasition class tnımları **************************/
.rotate-all-enter {

}

.rotate-all-enter-active {
  animation: rotate-all ease-in-out 2s forwards;
}

.rotate-all-leave {

}

.rotate-all-leave-active {

}

@keyframes rotate-all {
  from {
    transform: rotateY(0);
  }
  to {
    transform: rotateY(1080deg);
  }
}

/************************** Kapalı kartınanimasyonları için gerekli olan trasition class tnımları **************************/

.rotate-enter {

}

.rotate-enter-active {
  animation: rotate-in ease-in-out .5s forwards;
}

.rotate-leave {

}

.rotate-leave-active {
  animation: rotate-out ease-in-out .5s forwards;
}

@keyframes rotate-in {
  from {
    transform: rotateY(90deg);
  }
  to {
    transform: rotateY(0deg);
  }
}

@keyframes rotate-out {
  from {
    transform: rotateY(0deg);
  }
  to {
    transform: rotateY(90deg);
  }
}
</style>
