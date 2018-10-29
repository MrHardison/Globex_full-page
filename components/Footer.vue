<template>
  <footer 
    class="footer">
    <div class="footer__wrap">
      <ul class="footer__links">
        <li><a
          href="/"
          class="footer__link">Fundraising</a></li>
        <li><a
          href="/"
          class="footer__link">About</a></li>
        <li><a
          href="/"
          class="footer__link">Pricing</a></li>
        <li><a
          href="/"
          class="footer__link">Contact us</a></li>
      </ul>
      <ul class="footer__links">
        <li><a
          href="/"
          class="footer__link_min">Terms of use</a></li>
        <li><a
          href="/"
          class="footer__link_min">Cookie policy </a></li>
        <li><a
          href="/"
          class="footer__link_min">Legal information</a></li>
      </ul>
    </div>
    <div class="footer__wrap">
      <div class="footer__socials">
        <a
          :href="'https://twitter.com/GlobexApp'"
          target="_blank">
          <img
            src="/img/twitter.svg"
            alt="Twitter">
        </a>
        <a
          :href="'https://www.linkedin.com/company/globexapp'"
          target="_blank">
          <img
            src="/img/linkedin.svg"
            alt="Linkedin">
        </a>
        <a
          :href="'https://www.facebook.com/GlobexApp'"
          target="_blank">
          <img
            src="/img/facebook.svg"
            alt="Facebook">
        </a>
        <a
          :href="'https://www.instagram.com/globexapp'"
          target="_blank">
          <img
            src="/img/instagram.svg"
            alt="Instagram">
        </a>
        <a
          :href="''"
          target="_blank">
          <img
            src="/img/youtube.svg"
            alt="Youtube">
        </a>
        <a
          :href="'https://plus.google.com/u/3/b/110802867324501050207/'"
          target="_blank">
          <img
            src="/img/googleplus.svg"
            alt="Googleplus">
        </a>
      </div>
      <div class="footer__copy">
        Copyright &copy; 2018 Globex Financial Solution Ltd.
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  props: {}
}
</script>
<style scoped lang="sass">
  @import './footer'
</style>
