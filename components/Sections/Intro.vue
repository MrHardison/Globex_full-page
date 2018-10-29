<template>
  <section class="screen screen__intro">
    <div class="container">
      <div
        class="screen__info screen__info_intro">
        <transition name="text">
          <div v-show="show">
            <h1 class="h1">Free customer-centric global digital bank</h1>
            <p class="text">
              App-based digital bank designed to provide free of charge basic banking and revolutionary customer-focused financial products and services for people across the globe.
            </p>
            <h3 class="h3">Would you like to get early access?</h3>
            <form class="screen__form">
              <div class="input-box">
                <input
                  class="input-box__input" 
                  type="text" 
                  name="email" 
                  placeholder="your e-mail here"
                  autofocus>
              </div>
            </form>
            <div class="screen__buttons">
              <Button class="btn btn_blue">Follow updates</Button>
              <Button
                target="_blank"
                class="btn btn_red">Watch Video</Button>
            </div>
          </div>
        </transition>
      </div>
      <transition name="slideDown">
        <div v-show="show">
          <PhoneDemo
            :src="'/img/section_1_image.png'"
            class="screen__intro__mockup mockup mockup_big"/>
        </div>
      </transition>
      <div class="screen__links">
        <AppLink
          :href="''"
          class="app-link app-link_apple"/>
        <AppLink
          :href="''"
          class="app-link app-link_google"/>
      </div>
    </div>
  </section>
</template>

<script>
import Button from '~/components/Button.vue'
import PhoneDemo from '~/components/PhoneDemo.vue'
import AppLink from '~/components/AppLink.vue'

export default {
  name: 'Intro',
  components: {
    Button,
    PhoneDemo,
    AppLink
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
.slideDown-enter-active,
.slideDown-leave-active {
  animation: image 1s ease-out;
}
@keyframes text {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes image {
  from {
    opacity: 0;
    transform: translate3d(0, 2000px, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
</style>
