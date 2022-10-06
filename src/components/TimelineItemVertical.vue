<template>
  <div>
    <div class="flex">
      <div class="inline-flex flex-col items-center">
        <div class="bg-slate-800 text-gray-50 font-semibold text-lg w-8 h-12 rounded inline-flex items-center justify-center select-none">
          {{ props.label }}
        </div>
        <div class="min-h-[128px] h-full border border-dashed w-px my-4" v-if="!hideLine"></div>
      </div>

      <div class="ml-4">
        <h3 class="font-semibold mb-2 text-lg">
          {{ props.header }}
        </h3>
        <slot name="content"></slot>

        <p class="text-gray-700 mb-5">
          <slot></slot>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  label: {
    type: String,
    default: "1",
  },
  header: {
    type: String,
    default: "",
  },
  hideLine: {
    type: Boolean,
    default: false,
  },
});
</script>

<style scoped></style>
