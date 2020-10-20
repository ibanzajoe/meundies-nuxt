<template>
  <div class="side-bar-header flex items-end">
    <div v-if="type != 'social'" class="icon">
      <img class="header-icon" :src="headerImage" />
    </div>
    <div class="title">
      <span v-if="type == 'social'">#</span>{{title}}
    </div>
    <div class="subtitle">
      {{subtitle}}
    </div>
  </div>
</template>

<script>
import BullsEye from '@/assets/images/bullseye.png'
import Diamond from '@/assets/images/diamond.png'
export default {
  name: 'sidebar-header',
  props: {
    title: {
      type: String,
      default: 'Missions'
    },
    subtitle: {
      type: String,
      default: `Let's do this for more points!`
    },
    type: {
      type: String,
      default: 'mission'
    }
  },
  computed: {
    headerImage() {
      if (this.type == 'mission') return BullsEye
      if (this.type == 'redeem') return Diamond
    }
  }
}
</script>

<style scoped>
.side-bar-header {
  margin-bottom: 24px;
  letter-spacing: 0.25px;
}
.header-icon {
  width: 32px;
  margin-bottom: 1px;
  margin-right: 4px;
}
.title {
  font-size: 24px;
  font-weight: bold;
  line-height: 1;
}
.subtitle {
  margin-left: 8px;
  font-size: 15px;
  line-height: 1;
}
</style>