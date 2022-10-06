<template>
  <div class="flex w-full justify-between items-center rounded px-2 py-1 my-1 hover:bg-indigo-600 hover:text-white cursor-pointer" @click="handleToggle()">
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  to: {
    type: String,
    default: "",
  },
});
const emit = defineEmits(["onToggle"]);

function handleToggle() {
  emit("onToggle");
  console.log("toggle!");
  if (props.to) {
    ///router push
  }
}
</script>

<style scoped></style>
