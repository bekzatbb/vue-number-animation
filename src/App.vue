<template>
  Type A Number: <input v-model.number="number" />
  <p class="big-number">{{ tweened.toFixed(0) }}</p>
</template>

<script>
import { gsap } from "gsap"

export default {
  data() {
    return {
      number: 0,
      tweened: 0
    }
  },
  watch: {
    number(n) {
      gsap.to(this, { duration: 0.5, tweened: Number(n) || 0 })
    }
  }
}
</script>

<style scoped>
.big-number {
  font-weight: bold;
  font-size: 2em;
}
</style>
