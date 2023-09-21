<template>
  <div v-click class="flip-container">
    <slot />
  </div>
</template>

<style>
.flip-container.slidev-vclick-target {
  rotate: 0.5turn;
  transition: rotate 0.2s ease-in-out;
}

.flip-container.slidev-vclick-hidden {
  rotate: 0turn;
  opacity: 1 !important;
  pointer-events: initial !important;
}
</style>
