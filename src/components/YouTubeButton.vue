<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 cursor-pointer text-white rounded border-2 border-orange-600 bg-orange-500 hover:bg-orange-600 hover:text-white transition-colors"
    >
    <slot></slot>
    </a
  >
</template>

<script setup>
const props = defineProps({
    href: String
})
</script>