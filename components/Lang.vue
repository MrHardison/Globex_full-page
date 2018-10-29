<template>
  <div 
    :class="{open: showLangs}"
    class="lang">
    <img
      src="/img/en.svg"
      alt="En"
      @click="showLangs = !showLangs">
    <ul class="lang-list">
      <li
        class="item lang__en"
        @click="selectLang">
        <img
          src="/img/en.svg"
          alt="En">
      </li>
      <li
        class="item lang__en"
        @click="selectLang">
        <img
          src="/img/en.svg"
          alt="En">
      </li>
      <li
        class="item lang__en"
        @click="selectLang">
        <img
          src="/img/en.svg"
          alt="En">
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Lang',
  data() {
    return {
      list: {},
      showLangs: false
    }
  },
  methods: {
    selectLang() {
      this.showLangs = false
    }
  }
}
</script>
<style scoped lang="sass">
  @import './lang'
</style>
