<!-- v2 -->
<template>
  <div class="ui-table-actions">
    <div class="actions">
      <slot name="title">
        <UiActionsTitle>
          {{ title }}
        </UiActionsTitle>
      </slot>
      <slot />
    </div>
    <div v-if="slots.groupedBy">
      <slot name="groupedBy" />
    </div>
  </div>
</template>

<script setup lang="ts">
import UiActionsTitle from '@core/components/ui/actions-title/UiActionsTitle.vue'

defineProps<{
  title?: string
}>()

const slots = defineSlots<{
  default(): any
  title(): any
  groupedBy?(): any
}>()
</script>

<style scoped lang="postcss">
.ui-table-actions {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-block: 0.4rem;
  border-bottom: 0.1rem solid var(--color-neutral-border);

  .actions {
    display: flex;
    align-items: center;
    gap: 2.4rem;
  }
}
</style>
