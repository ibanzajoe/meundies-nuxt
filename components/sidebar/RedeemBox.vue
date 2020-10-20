<template>
  <div class="redeem-box flex">
    <div class="title-bar flex items-center justify-center">
      <h2 class="main-label">
        {{label}}
      </h2>
      <p class="sub-label">
        {{sublabel}}
      </p>
    </div>
    <div class="button-box flex items-center justify-center">
      <span class="on-hover">Redeem now</span>
      <span class="not-hover">500 pts</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'redeemBox',
  props: {
    label: {
      type: String,
      default: '10% off entire order'
    },
    sublabel: {
      type: String,
      default: 'expires in 31 days'
    }
  }
}
</script>

<style scoped>
.redeem-box {
  height: 80px;
  background-color: var(--color-light-green);
  border: 1px solid var(--color-green);
  text-align: center;
}
.title-bar {
  flex: 1 1;
  flex-direction: column;
}
.main-label {
  font-size: 21px;
  font-weight: bold;
  line-height: 1.15;
}
.sub-label {
  font-size: 10px;
}
.button-box {
  flex-basis: 80px;
  background-color: var(--color-green);
  font-size: 13px;
  color: white;
  text-decoration: underline;
  cursor: pointer;
  position: relative;
}

.button-box .on-hover {
  text-decoration: underline;
}

.button-box .on-hover, .button-box .not-hover {
  transition: all 200ms ease-in-out;
}

.button-box .on-hover, .button-box:hover .not-hover {
  opacity: 0;
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
}
.button-box:hover .on-hover, .button-box .not-hover {
  opacity: 1;
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
}
</style>