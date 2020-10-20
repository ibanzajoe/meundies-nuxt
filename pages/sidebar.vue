<template>
  <div class="meundies-sidebar">
    <TopBar />
    <div class="side-bar-body">
      <CurrentPoint points="50" />
      <p class="activity-link">View all my activities ></p>
      <div class="missions">
        <SideBarHeader title="Missions" subtitle="Let's do this for more points!" type="mission" />
        <transition-group name="fade">
          <MissionTodo v-if="mission.includes('1')" :key="1" points="10" label="1 min Survey" sublabel="Take a short and simple survey" />
          <MissionTodo v-if="mission.includes('2')" :key="2" points="100" label="Capture & Share" sublabel="Capture 30 secs video of our product and share in instagram" />
        </transition-group>
      </div>
      <div class="redeem">
        <SideBarHeader title="Redeem" subtitle="Get your favorite rewards" type="redeem" />
        <transition-group name="fade">
          <RedeemBox v-if="mission.includes('3')" :key="3" label="10% off entire order" sublabel="expires in 31 days" />
        </transition-group>
        
      </div>

      <div class="social">
        <div class="social-inner">
          <SideBarHeader title="MeUndies" subtitle="See what everyone's sharing" type="social" />
          <transition-group name="fade">
            <img v-if="mission.includes('4')" :key="4" :src="images" />
          </transition-group>
          
        </div>
      </div>
    </div>
    <div class="bot-bar">
      <div class="footer-info flex items-center justify-center">
        Powered by
        <img class="fanbird" :src="fanbird" />
      </div>
    </div>
  </div>
</template>

<script>
import TopBar from "@/components/sidebar/TopBar"
import CurrentPoint from '@/components/sidebar/CurrentPoint'
import SideBarHeader from "@/components/sidebar/Header"
import MissionTodo from '@/components/sidebar/MissionTodo'
import RedeemBox from '@/components/sidebar/RedeemBox'

import SocialImages from '@/assets/images/social-images.png'
import FanBird from '@/assets/images/Fanbird.png'
export default {
  name: 'sidebar',
  components: { TopBar, CurrentPoint, SideBarHeader, MissionTodo, RedeemBox },
  mounted() {
    let _this = this
    setTimeout(function() {
      _this.mission.push('1')
    }, 250)
    setTimeout(function() {
      _this.mission.push('2')
    }, 500)
    setTimeout(function() {
      _this.mission.push('3')
    }, 1000)
    setTimeout(function() {
      _this.mission.push('4')
    }, 1500)
  },
  data() {
    return {
      images: SocialImages,
      fanbird: FanBird,
      mission: []
    }
  }
}
</script>

<style scoped>
.meundies-sidebar {
  max-width: 800px;
  width: 100%;
}

.activity-link {
  font-size: 12px;
  text-align: center;
  text-decoration: underline;
  margin-top: 12px;
  margin-bottom: 36px;
}

.missions, .redeem, .social-inner {
  padding: 0 45px;
  margin-bottom: 45px;
}

.missions {
  height: 250px;
}

.redeem {
  height: 150px;
}

.social-inner {
  margin-bottom: 0;
  height: 220px;
}

.social {
  background-color: var(--color-grey);
  padding: 24px 0;
}

.bot-bar {
  padding: 12px;
  font-size: 12px;
}

.fanbird {
  width: 92px;
}

.fade-enter {
  opacity: 0;
  transform: translateY(20px);
}
.fade-enter-to {
  transform: translateY(0);
}

.fade-enter-active, .fade-leave-active {
  transition: all 500ms linear;
}
</style>