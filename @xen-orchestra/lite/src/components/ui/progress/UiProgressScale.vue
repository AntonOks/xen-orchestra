<template>
  <p class="unit typo-body-regular-small">
    <span>{{ `0${unit}` }}</span>
    <span v-for="step in steps" :key="step"> {{ Math.round((maxValue / (steps + 1)) * step) }}{{ unit }} </span>
    <span>{{ maxValue }}{{ unit }}</span>
  </p>
</template>

<script lang="ts" setup>
withDefaults(
  defineProps<{
    maxValue?: number
    steps?: number
    unit?: string
  }>(),
  { maxValue: 100, steps: 1 }
)
</script>

<style lang="postcss" scoped>
.unit {
  color: var(--color-neutral-txt-secondary);
  display: flex;
  justify-content: space-between;
  letter-spacing: 0.04em;
  line-height: 16px;
}
</style>
