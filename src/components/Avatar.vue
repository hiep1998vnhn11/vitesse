<script setup lang="ts">
const props = defineProps({
  name: {
    type: String,
    default: '',
  },
})

const shortName = computed(() => props.name.slice(0, 2))
</script>

<template>
  <div class="avatar">
    <span>
      {{ shortName }}
    </span>
  </div>
</template>

<style lang="scss" scoped>
.avatar {
  border-radius: 50%;
  background: #2DCE89;
  width: 56px;
  height: 56px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}
</style>
