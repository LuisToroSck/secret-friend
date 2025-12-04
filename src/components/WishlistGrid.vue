<script setup>
import participants from '../data/participants'
</script>

<template>
  <section class="wishlist-root">
    <div class="grid">
      <article v-for="p in participants" :key="p.id" class="card">
        <div class="card-top">
          <img :src="p.avatar" :alt="p.name" class="avatar" />
          <div class="name">{{ p.name }}</div>
        </div>
        <ul class="wishes">
          <li v-for="(w, i) in p.wishes" :key="i">🎁 {{ w }}</li>
        </ul>
        <div class="footer">No se puede identificar al donante — ¡sorpresa!</div>
      </article>
    </div>
  </section>
</template>

<style scoped>
.wishlist-root {
  padding: 1rem 0 2rem;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 1.25rem;
  align-items: stretch;
}
.card {
  background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
  border: 1px solid rgba(255,255,255,0.04);
  padding: 1rem;
  border-radius: 14px;
  box-shadow: 0 6px 18px rgba(0,0,0,0.35);
  transition: transform 220ms ease, box-shadow 220ms ease;
  display: flex;
  flex-direction: column;
}
.card:hover {
  transform: translateY(-6px);
  box-shadow: 0 14px 30px rgba(0,0,0,0.5);
}
.card-top {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 0.6rem;
}
.avatar {
  width: 56px;
  height: 56px;
  border-radius: 999px;
  object-fit: cover;
  border: 2px solid rgba(255,255,255,0.06);
}
.name {
  font-weight: 700;
  font-size: 1.05rem;
  text-align: left;
}
.wishes {
  list-style: none;
  padding: 0;
  margin: 0.2rem 0 0.8rem 0;
  text-align: left;
  color: rgba(255,255,255,0.95);
}
.wishes li {
  padding: 0.35rem 0;
  font-size: 0.95rem;
}
.footer {
  margin-top: auto;
  font-size: 0.8rem;
  color: rgba(255,255,255,0.55);
  text-align: left;
}

@media (prefers-color-scheme: light) {
  .card {
    background: linear-gradient(180deg, #fff, #fbfbfb);
    border: 1px solid rgba(0,0,0,0.06);
    box-shadow: 0 8px 22px rgba(0,0,0,0.06);
  }
  .name { color: #213547 }
  .wishes { color: #213547 }
  .footer { color: #6b6b6b }
}
</style>
