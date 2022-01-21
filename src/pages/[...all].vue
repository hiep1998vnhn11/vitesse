<script setup lang="ts">
const { t } = useI18n()
</script>

<template>
  <div class="bg-white not-found">
    <div class="not-found-title">
      Oops! Something went wrong.
    </div>
    <div class="not-found-sub-title">
      Don’t be shy. Take a break. From us to you.<br> We won’t tell ...
    </div>
    <div>
      But if you really want to get back to work quickly, click on the button
      below or email<br> us at support@benefitssolution.com.sg for help.
    </div>
    <router-link to="/" class="btn button">
      RESTART
    </router-link>

    <div class="flex large-404-container items-center justify-end">
      <div class="large-404">
        4
      </div>
      <div class="large-404-image">
        <img src="/images/404.png" alt="404">
      </div>
      <div class="large-404">
        4
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.not-found {
  margin-top: 18px;
  padding: 130px 60px;
  background-image: url(/images/error-bg.png);
  overflow: auto;
  &-title {
    font-weight: bold;
    color: $color-primary;
    font-size: 64px;
    line-height: 75px;
  }
  &-sub-title {
    font-weight: 500;
font-size: 36px;
line-height: 42px;
margin-bottom: 40px;
  }
}

.button {
  background: $color-btn;
  padding:8px 36px;
  margin-top: 40px;
}

.large-404-container {
  .large-404 {
    font-size: 288px;
line-height: 337px;
color: $color-primary;
font-weight: bold;
  }

  .large-404-image {
    border-radius: 50%;
    width: 220px;
    height: 220px;
    background: $color-primary-light;
  }
}
</style>

<route lang="yaml">
meta:
  layout: 404
</route>
