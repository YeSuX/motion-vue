<script setup lang="ts">
import { Motion } from 'motion-v'

const container = {
  hidden: { opacity: 1, scale: 0 },
  visible: {
    opacity: 1,
    scale: 1,
  },
}

const items = {
  hidden: { y: 20, opacity: 0, scale: 0.85 },
  visible: {
    y: 0,
    opacity: 1,
  },
}

const list = [0, 1, 2, 3]
</script>

<template>
  <Motion
    as="ul"
    :variants="container"
    initial="hidden"
    animate="visible"
    :transition="{
      type: 'spring',
      delayChildren: 0.5,
      staggerChildren: 0.2,
    }"
    class="rounded-2xl overflow-hidden  list-none p-2  grid-cols-2 grid-rows-2 aspect-square bg-primary/20 w-1/3  grid"
  >
    <Motion
      v-for="(item, i) in list"
      :key="item"
      :variants="items"
      class="bg-primary rounded-full origin-center"
    />
  </Motion>
</template>
