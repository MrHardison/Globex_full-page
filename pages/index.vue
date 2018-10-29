<template>
  <div
    v-if="desktop"
    class="desktop">
    <div class="container">
      <Header
        :showButtons="showHeaderButtons"
        @toForm="currentSection = $event"/>
      <transition name="fade">
        <component :is="sections[currentSection]"/>
      </transition>
      
      <div 
        :class="{hidden: currentSection === sections.length - 1}"
        class="mouse">
        <div class="mouse__scroll"/>
      </div>
      <Wave/>
    </div>
  </div>
  <div
    v-else
    class="mobile">
    <Header
      :showButtons="showHeaderButtons"/>
    <div class="container_mobile">
      <section class="screen screen__intro">
        <div
          class="screen__info screen__info_intro">
          <h1 class="h1">Free customer-centric global digital bank</h1>
          <p class="text">
            App-based digital bank designed to provide free of charge basic banking and revolutionary customer-focused financial products and services for people across the globe.
          </p>
        </div>
        <PhoneDemo
          :src="'/img/section_1_image.png'"
          class="screen__intro__mockup mockup mockup_big"/>
        <div class="screen__buttons">
          <Button
            target="_blank"          
            class="btn btn_red">Watch Video</Button>
        </div>
        <h3 class="h3">Would you like to get early access?</h3>
        <form class="screen__form">
          <div class="input-box">
            <input
              class="input-box__input" 
              type="text" 
              name="email" 
              placeholder="your e-mail here">
          </div>
        </form>
        <div class="screen__buttons">
          <div
            class="btn btn_blue"
            @click="confirm">Follow updates</div>
        </div>
      </section>

      <section class="screen screen__unified">
        <div class="screen__info screen__info_unified">
          <h1 class="h1">Revolutionary boarderless account</h1>
          <p class="text">
            Truly borderless banking account enables users to simply open and hold current accounts in any country of Globex presence.
          </p>
          <p class="text text_sm">Unified balance Main Screen</p>
        </div>
        <div class="screen__mockups">
          <swiper :options="swiperOption">
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_2_image_1.png'"
                class="mockup mockup_small"/>
            </swiper-slide>
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_2_image_2.png'"
                class="mockup mockup_big"/>
            </swiper-slide>
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_2_image_3.png'"
                class="mockup mockup_small"/>
            </swiper-slide>
            <div
              slot="pagination"
              class="swiper-pagination"/>
          </swiper>
        </div>
      </section>

      <section class="screen screen__transfers">
        <div class="screen__info screen__info_transfers">
          <h1 class="h1">Free and instant money transfers across the globe</h1>
          <p class="text">
            A range of options to make social, banking and online money transfers around the world at the best real currency exchange rates, while <span class="text__highlight">saving up to 7%</span> on each transaction.
          </p>
          <p class="text text_sm">Choose transfer type screen</p>
        </div>
        <div class="screen__mockups">
          <swiper :options="swiperOption">
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_3_image_1.png'"
                class="mockup mockup_small"/>
            </swiper-slide>
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_3_image_2.png'"
                class="mockup mockup_big"/>
            </swiper-slide>
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_3_image_3.png'"
                class="mockup mockup_small"/>
            </swiper-slide>
            <div
              slot="pagination"
              class="swiper-pagination"/>
          </swiper>
        </div>
      </section>

      <section class="screen screen__cards">
        <div class="screen__info screen__info_cards">
          <h1 class="h1">Free spending and cashout globally</h1>
          <p class="text">
            Card solution perfectly suitable for spending and cahsouts globally without any fees and at the best currency exchange rate.
          </p>
        </div>
        <div class="screen__cards-wrap">
          <div class="card-block card-block_1">
            <img
              src="/img/card_1.png"
              alt="Card1">
          </div>
          <div class="card-block card-block_2">
            <img
              src="/img/card_2.png"
              alt="Card2">
          </div>
        </div>
      </section>

      <section class="screen screen__services">
        <div class="screen__info screen__info_services">
          <h1 class="h1">Globex Marketplace</h1>
          <p class="text">
            Multiple lending, deposits, insurance and other options provided by third-party financial institutions, competing centralised for each user application.
          </p>
          <p class="text text_sm">Services screen</p>
        </div>
        <div class="screen__mockups">
          <swiper :options="swiperOption">
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_5_image_1.png'"
                class="mockup mockup_small"/>
            </swiper-slide>
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_5_image_2.png'"
                class="mockup mockup_big"/>
            </swiper-slide>
            <swiper-slide>
              <PhoneDemo
                :src="'/img/section_5_image_3.png'"
                class="mockup mockup_small"/>
            </swiper-slide>
            <div
              slot="pagination"
              class="swiper-pagination"/>
          </swiper>
        </div>
      </section>

      <section class="screen screen__merchant">
        <div class="screen__info screen__info_merchant">
          <h1 class="h1">Global merchant</h1>
          <p class="text">
            The unique merchant solution enables Globex Business users to accept online and offline payments from customers from around the world.
          </p>
        </div>
        <div class="screen__image-wrap">
          <img
            src="/img/section_6_image_mobile.png"
            alt="Image">
        </div>
      </section>
    </div>
    <Footer/>
  </div>
</template>

<script>
import debounce from 'lodash/debounce'
import throttle from 'lodash/throttle'
import Header from '~/components/Header.vue'
import Button from '~/components/Button.vue'
import AppLink from '~/components/AppLink.vue'
import PhoneDemo from '~/components/PhoneDemo.vue'
import Wave from '~/components/Wave.vue'
import Cards from '~/components/Sections/Cards.vue'
import Intro from '~/components/Sections/Intro.vue'
import Merchant from '~/components/Sections/Merchant.vue'
import Services from '~/components/Sections/Services.vue'
import Transfers from '~/components/Sections/Transfers.vue'
import Unified from '~/components/Sections/Unified.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Header,
    Button,
    AppLink,
    PhoneDemo,
    Wave,
    Cards,
    Intro,
    Merchant,
    Services,
    Transfers,
    Unified,
    Footer
  },
  data() {
    return {
      sections: [
        'Intro',
        'Unified',
        'Transfers',
        'Cards',
        'Services',
        'Merchant'
      ],
      currentSection: 0,
      scrollTop: null,
      scrollBottom: null,
      desktop: true,
      swiperOption: {
        autoplay: {
          delay: 3000
        },
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  computed: {
    showHeaderButtons() {
      return this.currentSection === 0 ? false : true
    }
  },
  mounted() {
    window.innerWidth <= 1023 ? (this.desktop = false) : (this.desktop = true)
    window.addEventListener(
      'wheel',
      throttle(this.onScroll, 1800, {
        leading: true,
        trailing: false
      })
    )
    window.addEventListener('resize', () => {
      window.innerWidth <= 1023 ? (this.desktop = false) : (this.desktop = true)
    })
  },
  methods: {
    onScroll(e) {
      if (e.deltaY > 0) {
        if (this.currentSection === this.sections.length - 1) {
          return
        } else if (this.currentSection >= 0) {
          ++this.currentSection
        }
      }
      if (e.deltaY < 0) {
        if (this.currentSection === 0) {
          return
        }
        --this.currentSection
      }
    },
    confirm() {
      console.log(1)
    }
  }
}
</script>

<style lang="sass">
.fade-enter-active,
.fade-leave-active
  animation: fade .5s ease-out

@keyframes fade
  from
    opacity: 1
  to
    opacity: 0
</style>
