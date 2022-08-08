<template>
  <footer
    v-if="$slidev.nav.currentLayout !== 'intro-image' && $slidev.nav.currentLayout !== 'section'"
    class="absolute bottom-0 right-0 p-2"
  >
    {{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}
  </footer>
</template>
