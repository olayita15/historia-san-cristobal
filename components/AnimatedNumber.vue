<script setup lang="ts">
import { nextTick, onBeforeUnmount, onMounted, ref } from 'vue'
import { onSlideEnter, onSlideLeave } from '@slidev/client'

const props = withDefaults(defineProps<{
  value: number
  duration?: number
  prefix?: string
  suffix?: string
}>(), {
  duration: 1600,
  prefix: '',
  suffix: '',
})

const displayed = ref(0)
let frame = 0
let delay = 0

function stop() {
  cancelAnimationFrame(frame)
  window.clearTimeout(delay)
  displayed.value = 0
}

function animate() {
  stop()
  delay = window.setTimeout(() => {
    const startedAt = performance.now()
    const tick = (now: number) => {
      const progress = Math.min((now - startedAt) / props.duration, 1)
      displayed.value = Math.round(props.value * (1 - (1 - progress) ** 3))
      if (progress < 1) frame = requestAnimationFrame(tick)
    }
    frame = requestAnimationFrame(tick)
  }, 220)
}

onMounted(async () => { await nextTick() })
onSlideEnter(animate)
onSlideLeave(stop)
onBeforeUnmount(stop)
</script>

<template>
  <span class="animated-number">{{ prefix }}{{ displayed.toLocaleString('es-CO') }}{{ suffix }}</span>
</template>
