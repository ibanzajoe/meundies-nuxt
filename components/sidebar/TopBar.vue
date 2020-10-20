<template>
  <div class="top-bar flex items-center justify-between">
    <div class="login">
      Hi Jaelen!
    </div>
    <div class="logo">
      <img class="logo-image" :src="logo" />
    </div>
    <div class="close">
      <img class="close-icon" :src="close" />
    </div>
  </div>
</template>

<script>
import BrandLogo from '@/assets/images/logo.png'
import Close from '@/assets/images/X.png'
export default {
  data() {
    return {
      logo: BrandLogo,
      close: Close
    }
  }
}
</script>

<style scoped>
.top-bar {
  width: 100%;
  padding: 2.5rem;
}
.login, .logo, .close {
  flex-basis: 33%;
}
.login {
  font-size: 15px;
}
.logo .logo-image {
  max-width: calc(236px/2);
  margin: 0 auto;
}
.close-icon {
  width: 16px;
  margin-left: auto;
}
</style>