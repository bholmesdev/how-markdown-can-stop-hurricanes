<template>
  <video
    class="rounded-lg"
    :controls="controls ?? false"
    :class="props.class"
    autoplay
    loop
    playsinline
    :src="src"
  />
</template>

<script setup>
const props = defineProps(["src", "class", "controls"]);
</script>
