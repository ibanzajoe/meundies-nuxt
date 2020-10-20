<template>
  <div class="mission-todo">
    <div class="absolute-box">
      {{points}}<span class="pts">pts</span>
    </div>
    <div class="main-label">
      {{label}}
    </div>
    <div class="sub-label">
      {{sublabel}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'MissionTodo',
  props: {
    points: {
      type: String,
      default: '10'
    },
    label: {
      type: String,
      default: '1 min Survey'
    },
    sublabel: {
      type: String,
      default: 'Take a short and simple survey'
    }
  }
}
</script>

<style scoped>
.mission-todo {
  border: 1px solid var(--color-green);
  padding: 20px;
  margin-bottom: 28px;
  position: relative;
  height: 80px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.absolute-box {
  position: absolute;
  top: 0;
  transform: translateY(-50%);
  right: -10px;
  background-color: var(--color-green);
  padding: 6px 8px;
  border-radius: 10px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  letter-spacing: 1px;
  line-height: 1.25;
}

.pts {
  font-size: 12px;
}

.main-label {
  font-size: 18px;
  font-weight: bold;
}
.sub-label {
  font-size: 14px;
}
</style>