<template>
  <header class="px-4">
    <v-container class="pa-0">
      <nuxt-link to="/" class="logo">
        <v-img :src="isLogo" width="180"></v-img>
      </nuxt-link>
      <a href="javascript:void(0)" class="hamburger">
        <span></span><span></span><span></span>
      </a>
    </v-container>
  </header>
</template>

<script>
export default {
  data () {
    return {
      isLogo: require('@/assets/images/logo-InfinityStudio--horiz.svg'),
    }
  }
}
</script>


<style lang="scss" scoped>
header {
  width: 100%;
  height: 50px;
  position: fixed;
  top: 0;
  left: 0;
  background-color: rgba($color-primary, 0.8);
  backdrop-filter: blur(4px);
  z-index: 10;
  .logo {
    height: 18px;
    margin: 16px 0;
    float: left;
  }
  .hamburger {
    width: 50px;
    height: 50px;
    float: right;
    position: relative;
    // position: absolute;
    // top: 0;
    // right: 12px;
    padding: 13px;
    span {
      height: 2px;
      width: 24px;
      margin: 2px 0;
      float: left;
      background-color: $color-white;
      border-radius: 2px;
    }
  }
}
</style>
