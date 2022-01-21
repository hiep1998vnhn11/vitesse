<script setup lang="ts">
const props = defineProps({
  show: {
    type: Boolean,
    default: false,
  },
})
</script>

<template>
  <div class="filter" :class="{ show: show }">
    <div class="filter-header">
      <h3>
        Filter
      </h3>
      <a class="cursor-pointer">
        Reset all filter
      </a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.filter {
  height: 100vh;
  position: fixed;
  z-index: 999;
  background: #fff;
  top: 0;
  right: 0;
  padding: 16px;
    width: $filter-width;
  transition: transform 0.3s ease-in-out;
  transform: translateX(100%);
  &.show {
    transition: transform 0.3s ease-in-out;
    transform: translateX(0);
  }
  &-header {
      display: flex;
        justify-content: space-between;
        height: 100px;
        padding-top: 20px;
        border-bottom: solid 1px rgba(0,0,0,0.1);
        a {
            color: $color-text;
        }
        h3 {
            font-weight: 500;
font-size: 30px;
line-height: 35px;
        }
  }
}
</style>
