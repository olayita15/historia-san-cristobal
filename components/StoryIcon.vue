<script setup lang="ts">
withDefaults(defineProps<{ name: 'mountain' | 'land' | 'home' | 'leaf' | 'people' | 'scale' | 'megaphone' | 'road' }>(), { name: 'mountain' })
</script>

<template>
  <svg class="story-icon" viewBox="0 0 48 48" fill="none" aria-hidden="true">
    <template v-if="name === 'mountain'"><path d="m5 38 13-22 7 11 5-8 13 19"/><path d="M18 16l3 5 3-5"/></template>
    <template v-else-if="name === 'land'"><path d="M6 35c9-9 14 5 23-7 5-7 8-9 13-11"/><path d="M7 14h34M7 21h34M7 28h34M14 8v28M24 8v28M34 8v28"/></template>
    <template v-else-if="name === 'home'"><path d="m6 23 18-15 18 15v18H6V23Z"/><path d="M18 41V29h12v12"/></template>
    <template v-else-if="name === 'leaf'"><path d="M39 8C20 8 10 17 10 34c0 3 1 5 2 6 16 0 26-10 27-32Z"/><path d="M10 40c7-10 14-16 25-23"/></template>
    <template v-else-if="name === 'people'"><circle cx="17" cy="16" r="5"/><circle cx="32" cy="17" r="4"/><path d="M7 40c1-9 6-14 10-14s9 5 10 14M25 40c1-7 4-11 8-11s7 4 8 11"/></template>
    <template v-else-if="name === 'scale'"><path d="M24 7v33M14 12h20M9 18l5-6 5 6c0 5-10 5-10 0ZM29 18l5-6 5 6c0 5-10 5-10 0ZM16 40h16"/></template>
    <template v-else-if="name === 'megaphone'"><path d="M7 27h8l17 8V13l-17 8H7v6Z"/><path d="M15 27l3 12h6l-2-10M36 20c3 2 3 6 0 8"/></template>
    <template v-else><path d="M6 35h36M10 35V20h12v15M27 35V11h11v24"/><path d="M14 25h4M14 30h4M31 17h3M31 23h3M31 29h3"/></template>
  </svg>
</template>
