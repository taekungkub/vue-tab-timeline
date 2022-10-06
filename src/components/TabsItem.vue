<template>
  <div>
    <div class="wrapper">
      <div
        class="line left"
        :class="{
          '!bg-transparent': props.hideLeft,
        }"
        v-if="!start"
      ></div>
      <div class="timeline-item" @click="$emit('toggle')">
        <div
          class="timeline-inner"
          :class="{
            'bg-green-500 border border-transparent': props.active,
            'bg-slate-600 border hover:border-green-500': !props.active,
          }"
        >
          <slot></slot>
        </div>
      </div>
      <div
        class="line right"
        :class="{
          '!bg-transparent': props.hideRight,
        }"
        v-if="!end"
      ></div>
    </div>
    <div class="label">{{ props.label }}</div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  start: {
    type: Boolean,
    default: false,
  },
  end: {
    type: Boolean,
    default: false,
  },
  hideLeft: {
    type: Boolean,
    default: false,
  },
  hideRight: {
    type: Boolean,
    default: false,
  },
  active: {
    type: Boolean,
    default: false,
  },
  label: {
    type: String,
    default: "",
  },
});
</script>

<style scoped>
.wrapper {
  @apply relative flex items-center justify-center;
}
.timeline-item {
  @apply bg-slate-800 p-1.5 lg:p-2.5 rounded-xl inline-flex cursor-pointer;
}

.timeline-inner {
  @apply px-3 py-1 rounded-lg   text-white font-black select-none transition duration-200;
}

.line.left {
  @apply py-2  bg-slate-800 w-full;
}

.line.right {
  @apply py-2  bg-slate-800 w-full;
}

.label {
  @apply hidden md:block text-center font-bold mt-3 text-lg;
}
</style>
