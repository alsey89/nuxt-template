<script setup lang="ts">
import type { HTMLAttributes } from 'vue'
import { Primitive, type PrimitiveProps } from 'radix-vue'
import { type ButtonVariants, buttonVariants } from '.'
import { cn } from '@/lib/utils'

interface Props extends /* @vue-ignore */ PrimitiveProps {
  variant?: ButtonVariants['variant']
  size?: ButtonVariants['size']
  as?: string
  asChild?: boolean
  class?: HTMLAttributes['class']
}

const props = withDefaults(defineProps<Props>(), {
  as: 'button',
})
</script>

<template>
  <!-- `asChild` prop enables the `Primitive` component to render its content directly into its parent,
  omitting an extra DOM wrapper. This is useful for maintaining semantic HTML and reducing unnecessary nesting,
  by allowing the component to pass all props, slots, and event listeners to its child, thus avoiding additional element
  layers.
  Useful for flexible UI composition and ensuring clean, semantic HTML structures. -->
  <Primitive :as="as" :as-child="asChild" :class="cn(buttonVariants({ variant, size }), props.class)">
    <slot />
  </Primitive>
</template>
