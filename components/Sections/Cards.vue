<template>
  <section class="screen screen__cards">
    <div class="container">
      <div class="screen__cards-wrap">
        <transition name="card1">
          <div
            v-show="show"
            class="card-block card-block_1">
            <img
              src="/img/card_1.png"
              alt="Card1">
          </div>
        </transition>
        <transition name="card2">
          <div
            v-show="show"
            class="card-block card-block_2">
            <img
              src="/img/card_2.png"
              alt="Card2">
          </div>
        </transition>
      </div>
      <transition name="text">
        <div v-show="show">
          <div class="screen__info screen__info_cards">
            <h1 class="h1">Free spending and cashout globally</h1>
            <p class="text">
              Card solution perfectly suitable for spending and cahsouts globally without any fees and at the best currency exchange rate.
            </p>
          </div>
        </div>
      </transition>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Cards',
  data() {
    return {
      show: false
    }
  },
  mounted() {
    this.show = true
  }
}
</script>

<style scoped>
.text-enter-active,
.text-leave-active {
  animation: text 1.5s ease-in;
}
.card1-enter-active,
.card1-leave-active {
  animation: card1 1s ease-out;
}
.card2-enter-active,
.card2-leave-active {
  animation: card2 1s ease-out;
}
@keyframes text {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes card1 {
  from,
  50% {
    opacity: 0;
    transform: translate3d(0, 500px, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
@keyframes card2 {
  from {
    opacity: 0;
    transform: translate3d(0, 700px, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
</style>
