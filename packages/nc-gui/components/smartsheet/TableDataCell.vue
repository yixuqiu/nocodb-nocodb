<script lang="ts" setup>
import { CellClickHookInj, CurrentCellInj, createEventHook, ref } from '#imports'

const el = ref<HTMLElement>()

const cellClickHook = createEventHook()

provide(CellClickHookInj, cellClickHook)

provide(CurrentCellInj, el)
</script>

<template>
  <td ref="el" class="select-none" @click="cellClickHook.trigger($event)">
    <slot />
  </td>
</template>
