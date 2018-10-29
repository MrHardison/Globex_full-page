<template>
  <section class="screen screen__transfers">
    <div class="container">
      <transition name="text">
        <div v-show="show">
          <div class="screen__info screen__info_transfers">
            <h1 class="h1">Free and instant money transfers across the globe</h1>
            <p class="text">
              A range of options to make social, banking and online money transfers around the world at the best real currency exchange rates, while <span class="text__highlight">saving up to 7%</span> on each transaction.
            </p>
          </div>
        </div>
      </transition>
      <div class="screen__mockups">
        <transition name="image1">
          <PhoneDemo
            v-show="show"
            :src="'/img/section_3_image_1.png'"
            class="mockup mockup_small"/>
        </transition>
        <transition name="image2">
          <PhoneDemo
            v-show="show"
            :src="'/img/section_3_image_2.png'"
            class="mockup mockup_big mockup_big-centered"/>
        </transition>
        <transition name="image3">
          <PhoneDemo
            v-show="show"
            :src="'/img/section_3_image_3.png'"
            class="mockup mockup_small"/>
        </transition>  
      </div>
    </div>
  </section>
</template>

<script>
import PhoneDemo from '~/components/PhoneDemo.vue'
export default {
  name: 'Transfers',
  components: {
    PhoneDemo
  },
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
.image2-enter-active,
.image2-leave-active {
  animation: image1 1s ease-out;
}
.image3-enter-active,
.image3-leave-active {
  animation: image2 1.3s ease-out;
}
.image1-enter-active,
.image1-leave-active {
  animation: image3 1.2s ease-out;
}
@keyframes text {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes image1 {
  from,
  10% {
    opacity: 0;
    transform: translate3d(0, 2000px, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
@keyframes image2 {
  from,
  30% {
    opacity: 0;
    transform: translate3d(0, 2000px, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
@keyframes image3 {
  from,
  20% {
    opacity: 0;
    transform: translate3d(0, 2000px, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
</style>
