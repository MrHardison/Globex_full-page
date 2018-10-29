<template>
  <section class="screen screen__unified">
    <div class="container">
      <div class="screen__mockups">
        <transition name="image1">
          <PhoneDemo
            v-show="show"
            :src="'/img/section_2_image_1.png'"
            class="mockup mockup_small"/>
        </transition>
        <transition name="image2">
          <PhoneDemo
            v-show="show"
            :src="'/img/section_2_image_2.png'"
            class="mockup mockup_big mockup_big-centered"/>
        </transition>
        <transition name="image3">
          <PhoneDemo
            v-show="show"
            :src="'/img/section_2_image_3.png'"
            class="mockup mockup_small"/>
        </transition>  
      </div>
      <transition name="text">
        <div v-show="show">
          <div class="screen__info screen__info_unified">
            <h1 class="h1">Revolutionary boarderless account</h1>
            <p class="text">
              Truly borderless banking account enables users to simply open and hold current accounts in any country of Globex presence.
            </p>
          </div>
        </div>
      </transition>
    </div>
  </section>
</template>

<script>
import PhoneDemo from '~/components/PhoneDemo.vue'
export default {
  name: 'Unified',
  components: { PhoneDemo },
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
.image1-enter-active,
.image1-leave-active {
  animation: image1 1s ease-out;
}
.image2-enter-active,
.image2-leave-active {
  animation: image2 1.3s ease-out;
}
.image3-enter-active,
.image3-leave-active {
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
