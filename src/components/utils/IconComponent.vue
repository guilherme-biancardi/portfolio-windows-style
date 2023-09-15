<template>
  <SvgIcon type="mdi" :path="path" :size="size"></SvgIcon>
</template>

<script setup lang="ts">
import type { Icon } from '@/ts/types';
import SvgIcon from '@jamescoyle/vue-icon'

defineProps<Icon>()
</script>

<style scoped>
svg{
  display: grid;
  place-items: center;
}
</style>
