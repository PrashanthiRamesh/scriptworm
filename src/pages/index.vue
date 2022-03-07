<script setup lang="ts">
import { useUserStore } from '~/stores/user'

const user = useUserStore()
const name = ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name.value)
    router.push(`/hi/${encodeURIComponent(name.value)}`)
}

const { t } = useI18n()
</script>

<template>
  <div class="main-section">
    <div i-carbon-debug inline-block />
    <div>Script Worm</div>
    <em text-sm opacity-75>Web developers' hideout</em>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
