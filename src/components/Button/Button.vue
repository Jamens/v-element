<template>
  <button
    ref="_ref"
    class="vk-button"
    :class="{
      [`vk-button--${type}`]: type,
      [`vk-button--${size}`]: size,
      'is-plain': plain,
      'is-round': round,
      'is-circle': circle,
      'is-disabled': disabled
    }"
    :disabled="disabled"
    :autofocus="autofocus"
    :type="NativeType"
  >
    <slot />
  </button>
</template>
<script lang="ts" setup>
import {ref} from "vue"
import type {ButtonProps} from '@/components/Button/types'
defineOptions({
  name: "VButton"
})
withDefaults(defineProps<ButtonProps>(), {
  NativeType: 'button'
})
const _ref = ref<HTMLButtonElement>()
defineExpose({
  ref: _ref
})
</script>
<style>
.vk-button{
  background: var(--main-bg-color);
}
</style>
