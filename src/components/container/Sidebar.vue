<script lang="ts" setup>
import { menus } from './container.data'
const props = defineProps({
  collapse: {
    type: Boolean,
    default: false,
  },
})

const emit = defineEmits(['toggleCollapse'])
</script>

<template>
  <div class="sidebar" :class="{ collapse: collapse }">
    <div class="sidebar-header">
      <a class="cursor-pointer" @click="emit('toggleCollapse')">
        <carbon-menu v-if="collapse" />
        <carbon-arrow-left v-else />
      </a>
    </div>
    <ul class="sidebar-menu">
      <router-link
        v-for="menu in menus"
        :key="menu.path"
        v-slot="{ href, navigate, isActive, isExactActive }"
        custom
        :to="menu.path"
      >
        <li class="sidebar-menu-item" :class="{ active: isExactActive }">
          <a :href="href" @click="navigate">
            <component :is="menu.icon" />
            <div class="sidebar-text">{{ menu.label }}</div>
          </a>
        </li>
      </router-link>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.sidebar {
  width: $sidebar-width;
  background: $color-primary;
  color: #fff;
  height: 100vh;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: width 0.3s;
  &-header {
    padding: $sidebar-padding;
    margin-bottom: 32px;
  }

  &-menu {
    display: flex;
    flex-direction: column;
    &-item {
      padding: 12px $sidebar-padding;
      transition: color 0.3s;
      word-wrap: none;
      height: 48px;

      &:hover,
      &.active {
        background: $color-primary-light;
        transition: color 0.3s;
      }
    }
  }
  &.collapse {
    width: $sidebar-collapse-width;
    .sidebar-text {
      display: none;
    }
  }
}
</style>
