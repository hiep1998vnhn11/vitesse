<script lang="ts" setup>
import Avatar from '../Avatar.vue'
const route = useRoute()
</script>
<template>
  <div class="header">
    <nav>
      <div class="header-title">
        {{ route.meta.title }}
      </div>
      <div class="flex">
        <div class="notification-container">
          <carbon-notification />
        </div>
        <div class="avatar-container">
          <Avatar name="Admin" />
        </div>
      </div>
    </nav>
  </div>
</template>

<style lang="scss" scoped>
.header {
  padding: 7px 0 0 0;
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: solid 1px rgba(0,0,0,0.1);
    padding-bottom: 20px;
    .header-title {
      font-weight: bold;
      font-size: 30px;
      line-height: 35px;
    }
    &-tabs {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 16px;
    }
    .avatar-container {
      padding-left: 32px;
      position: relative;
      &:after {
        width: 1px;
        height: 50%;
        top: 25%;
        left: 0;
        content: '';
        position: absolute;
        background: rgba(0,0,0,0.2);
      }
    }

    .notification-container {
      padding-right: 32px;
      display: flex;
      align-items: center;
    }
  }
}
</style>
