<script setup>
import WishlistGrid from './components/WishlistGrid.vue'
</script>

<template>
  <div class="app-wrap">
    <header class="hero">
      <div class="hero-inner">
        <h1>Amigo Secreto — Deseos</h1>
        <p class="lead">Aquí están los deseos de los participantes. No se permite registrar — solo mostrar.</p>
      </div>
    </header>

    <main>
      <WishlistGrid />
    </main>

    <footer class="footer">Organiza una entrega bonita — ¡Felices fiestas!</footer>
  </div>
</template>

<style scoped>
.app-wrap { color: inherit }
.hero {
  padding: 2rem 0 1rem;
  display: flex;
  justify-content: center;
}
.hero-inner { max-width: 880px }
.lead { color: rgba(255,255,255,0.8); margin-top: 0.4rem }
.footer { margin-top: 1.5rem; color: rgba(255,255,255,0.5); font-size: 0.95rem }

@media (prefers-color-scheme: light) {
  .lead { color: #354b5b }
}
</style>
