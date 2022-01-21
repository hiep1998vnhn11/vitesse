<script setup lang="ts">
const props = defineProps({
  hasTab: {
    type: Boolean,
    default: false,
  },
})
</script>

<template>
  <div class="content">
    <div v-if="hasTab" class="tabs">
      test
    </div>
    <slot />
  </div>
</template>
