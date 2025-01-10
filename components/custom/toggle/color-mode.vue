<script setup lang="ts">
import { Sun, Moon } from 'lucide-vue-next'
const colorMode = useColorMode()

const toggleTheme = () => {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark'
}
</script>

<template>
  <ClientOnly>
    <Switch
      :checked="colorMode.preference == 'dark'"
      @update:checked="toggleTheme"
    >
      <template #thumb>
        <Moon
          v-if="colorMode.preference === 'dark'"
          class="size-4 mx-auto my-0.5"
        />
        <Sun v-else class="size-4 mx-auto my-0.5" />
      </template>
    </Switch>
  </ClientOnly>
</template>
