<template>
  <div class="current-point flex items-center justify-center" :style="`background-image: url(${bgImage})`">
    <p class="label">Current points</p>
    <p class="points">{{points}}</p>
  </div>
</template>

<script>
import Confiti from '@/assets/images/confiti.png'
export default {
  props: {
    points: {
      type: String,
      default: '50'
    }
  },
  data () {
    return {
      bgImage: Confiti
    }
  }
}
</script>

<style scoped>

.current-point {
  height: 95px;
  width: 232px;
  margin: 0 auto;
  background-size: cover;
  text-align: center;
  flex-direction: column;
}
.label {
  font-size: 14px;
}
.points {
  font-size: 36px;
  line-height: 1.15;
  font-weight: bold;
}

</style>