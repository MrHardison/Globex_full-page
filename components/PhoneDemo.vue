<template>
  <div>
    <img
      :src="src" 
      class="mockup__img"
      alt="Image">
  </div>
</template>

<script>
export default {
  name: 'PhoneDemo',
  props: {
    src: {
      type: String,
      default: ''
    }
  }
}
</script>
<style scoped lang="sass">
  @import './phonedemo'
</style>
