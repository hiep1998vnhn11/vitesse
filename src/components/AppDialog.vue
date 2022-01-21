<script setup lang="ts">
const props = defineProps({
  show: {
    type: Boolean,
    default: false,
  },
})

const emit = defineEmits(['close'])
const showDialog = ref(false)
const showContainer = ref(false)

const handleClickDialog = (e: MouseEvent) => {
  e.stopPropagation()
  if (e.target instanceof HTMLElement) {
    const el = e.target as HTMLElement
    if (el.classList.contains('dialog')) emit('close')
  }
}

watch(() => props.show, (show) => {
  if (show) {
    showDialog.value = true
    setTimeout(() => showContainer.value = true, 0)
  }
  else {
    showContainer.value = false
    setTimeout(() => showDialog.value = false, 150)
  }
})
</script>

<template>
  <div v-if="showDialog" class="dialog" @click="handleClickDialog">
    <div class="dialog-container" :class="{active: showContainer}">
      <div class="dialog-header">
        <h3>Dialog</h3>
        <a class="cursor-pointer" @click="emit('close')">
          <carbon-time />
        </a>
      </div>
      <div class="dialog-content">
        <slot />
      </div>
      <div class="dialog-footer">
        <button>Close</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.dialog {
  position: fixed;
  z-index: 1050;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.2);
  display: flex;
  justify-content: center;
  align-items: center;

  &-container {
    background: #ffffff;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
    border-radius: 10px;
    min-width: 600px;
    transform: translateY(50vh);
      transition: transform 0.15s ease-in-out;

    &.active {
      transition: transform 0.15s ease-in-out;
      transform: translateY(0);
    }
    .dialog-header {
      display: flex;
      justify-content: space-between;
      height: 60px;
      padding-top: 20px;
      border-bottom: solid 1px rgba(0, 0, 0, 0.1);
    padding: 14px 30px;
    h3 {
      font-size: 20px;
      font-weight: bold;
    }
    }

    .dialog-content {
      padding: 30px;
    }

    .dialog-footer {
      display: flex;
      justify-content: flex-end;
      padding: 14px 30px;
    }
  }
}
</style>
