<template>
  <div
    class="grid py-5"
    :class="{
      'grid-cols-1': props.number === 1,
      'grid-cols-2': props.number === 2,
      'grid-cols-3': props.number === 3,
      'grid-cols-4': props.number === 4,
      'grid-cols-5': props.number === 5,
      'grid-cols-6': props.number === 6,
      'grid-cols-7': props.number === 7,
      'grid-cols-8': props.number === 8,
      'grid-cols-9': props.number === 9,
      'grid-cols-10': props.number === 10,
      'grid-cols-11': props.number === 11,
      'grid-cols-12': props.number === 12,
    }"
    v-if="!props.vertical"
  >
    <slot></slot>
  </div>

  <div v-if="props.vertical">
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  number: {
    type: Number,
    default: 0,
  },
  vertical: {
    type: Boolean,
    default: false,
  },
});
</script>

<style scoped></style>
