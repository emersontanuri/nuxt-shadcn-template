<script setup lang="ts">
import { Sun, Moon } from 'lucide-vue-next'
const colorMode = useColorMode()

const toggleTheme = () => {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark'
}
</script>

<template>
  <ClientOnly>
    <Button @click="toggleTheme" variant="ghost" size="icon">
      <Moon v-if="colorMode.preference === 'light'" />
      <Sun v-else />
    </Button>
  </ClientOnly>
</template>
