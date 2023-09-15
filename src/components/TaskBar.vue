<template>
  <nav class="task-bar" :style="{ backgroundColor: lightColorOpacity }">
    <ul class="bar-items">
      <li v-for="(item, index) in state.items" :key="index">
        <IconComponent :path="item.icon.path" :size="item.icon.size ?? 40"></IconComponent>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import type { Icon } from '@/ts/types'
import { mdiViewGrid } from '@mdi/js'
import { useCssVar } from '@vueuse/core'
import { computed, reactive } from 'vue'
import IconComponent from './utils/IconComponent.vue'

const lightColor = useCssVar('--light')
const lightColorOpacity = computed<string>(() => `${lightColor.value}bb`)

interface Item {
  icon: Icon
}

type State = {
  items: Item[]
}

const state = reactive<State>({
  items: [
    {
      icon: {
        path: mdiViewGrid
      }
    }
  ]
})
</script>

<style scoped>
.task-bar,
.bar-items {
  display: flex;
  align-items: center;
  justify-content: center;
}
.task-bar {
  width: 100%;
  height: 100%;
  backdrop-filter: blur(4px);
}

.bar-items {
  height: 100%;
}
</style>
