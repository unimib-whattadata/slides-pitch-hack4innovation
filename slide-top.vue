<script setup>
import { onMounted, onUnmounted } from 'vue'

const exportClass = 'is-slidev-export'

function syncExportClass() {
  if (typeof window === 'undefined' || typeof document === 'undefined')
    return

  const isExport = new URLSearchParams(window.location.search).has('print')
  document.documentElement.classList.toggle(exportClass, isExport)
}

onMounted(() => {
  syncExportClass()
  window.addEventListener('popstate', syncExportClass)
})

onUnmounted(() => {
  window.removeEventListener('popstate', syncExportClass)
  document.documentElement.classList.remove(exportClass)
})
</script>

<template>
  <div class="deck-progress" aria-hidden="true">
    <div class="deck-progress__track">
      <div
        class="deck-progress__bar"
        :style="{ width: `${($page / $nav.total) * 100}%` }"
      />
    </div>
  </div>
</template>

<style scoped>
.deck-progress {
  position: absolute;
  inset: auto 0 0;
  z-index: 60;
  pointer-events: none;
}

.deck-progress__track {
  width: 100%;
  height: 4px;
  overflow: hidden;
  background: rgba(255, 255, 255, 0.1);
  box-shadow: 0 -1px 0 rgba(255, 255, 255, 0.08);
}

.deck-progress__bar {
  height: 100%;
  width: 0;
  background: linear-gradient(90deg, #818cf8 0%, #34d399 100%);
  box-shadow: 0 0 18px rgba(129, 140, 248, 0.4);
  transition: width 0.35s cubic-bezier(0.22, 1, 0.36, 1);
}

@media (prefers-reduced-motion: reduce) {
  .deck-progress__bar {
    transition: none;
  }
}
</style>
