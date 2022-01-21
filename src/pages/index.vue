<script setup lang="ts">
import Sortable from 'sortablejs'

import { useUserStore } from '~/stores/user'

const user = useUserStore()
const name = ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name.value)
    router.push(`/hi/${encodeURIComponent(name.value)}`)
}
const showFilter = ref(false)
const array = [{
  id: 1,
  text: 'foo',
}, {
  id: 2,
  text: 'bar',
}, {
  id: 3,
  text: 'baz',
}]

const { t } = useI18n()
</script>

<template>
  <page-wrapper />
</template>

<route lang="yaml">
meta:
  title: Dashboard
</route>
