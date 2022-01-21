<script lang="ts" setup>
import Header from '~/components/container/Header.vue'
import Sidebar from '~/components/container/Sidebar.vue'

const sidebarCollapse = ref(false)
const toggleSidebar = () => {
  sidebarCollapse.value = !sidebarCollapse.value
}
onMounted(() => {
})

</script>
<template>
  <div class="default-layout">
    <Sidebar :collapse="sidebarCollapse" @toggleCollapse="toggleSidebar()" />
    <div class="content">
      <Header />

      <main>
        <router-view />
      </main>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.default-layout {
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  display: flex;

  .content {
    flex: 1;
    padding: 18px 30px;
    background: $color-background;
    overflow-y: auto;
  }
}
</style>
