<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{ document: string, page?: number }>()
const href = computed(() => `${import.meta.env.BASE_URL}slides/${props.document}${props.page ? `#page=${props.page}` : ''}`)
</script>

<template>
  <a :href="href" target="_blank" rel="noopener noreferrer"><slot /></a>
</template>
