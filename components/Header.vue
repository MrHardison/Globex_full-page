<template>
  <header 
    :showButtons="showButtons"
    class="header">
    <div class="header__inner">
      <Logo 
        :href="'/'"
        :src="'/img/logo.png'"
        class="logo"/>
      <div class="slogan">
        <span class="slogan__text">
          We are
          <a
            class="slogan__text_colored"
            href="https://blog.revolut.com/"
            target="_blank">
            fundraising!
          </a>
          😎
        </span>
      </div>
    </div>
    <div class="header__inner header__inner_end">
      <div
        :class="{visible: showButtons}"
        class="btns-block">
        <Button
          target="_blank" 
          class="btn btn_red">Watch Video</Button>
        <Button
          class="btn btn_blue"
          @click.native="$emit('toForm', 0)">Follow updates</Button>
      </div>
      <Lang/>
    </div>
  </header>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Button from '~/components/Button.vue'
import Lang from '~/components/Lang.vue'

export default {
  name: 'Header',
  components: { Logo, Button, Lang },
  props: {
    showButtons: {
      type: Boolean,
      default: true
    }
  }
}
</script>
<style scoped lang="sass">
  @import './header'
</style>
