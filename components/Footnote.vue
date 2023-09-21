<template>
  <footer
    :class="$style.footer + ' ' + props.class"
    class="fixed bottom-4 left-4 text-xs text-gray-400 leading-6"
  >
    <slot />
  </footer>
</template>

<script setup>
const props = defineProps({
  class: String,
});
</script>

<style module>
.footer > p {
  margin: 0.5em !important;
}
</style>
