<template>
  <header class="header">
    <div class="brand">
      <div class="logo">{{ logo.initials }}</div>
      <div>
        <h1>{{ logo.name }}</h1>
        <p>{{ logo.tagline }}</p>
      </div>
    </div>
    <nav class="nav" aria-label="主导航">
      <a
        v-for="item in navLinks"
        :key="item.label"
        class="nav-item"
        :href="item.href"
      >
        {{ item.label }}
      </a>
    </nav>
    <div class="actions">
      <button class="btn ghost">{{ secondaryAction }}</button>
      <button class="btn primary">{{ primaryAction }}</button>
    </div>
  </header>
</template>

<script setup>
const props = defineProps({
  logo: {
    type: Object,
    required: true,
  },
  navLinks: {
    type: Array,
    default: () => [],
  },
  primaryAction: {
    type: String,
    default: '开始体验',
  },
  secondaryAction: {
    type: String,
    default: '产品演示',
  },
});
</script>

<style scoped>
.header {
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  gap: 2rem;
  padding: 1.5rem 2rem;
  background: linear-gradient(135deg, rgba(76, 110, 245, 0.08), rgba(255, 255, 255, 0.6));
  border-radius: 24px;
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.7);
}

.brand {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.brand h1 {
  font-size: 1.4rem;
  margin: 0;
}

.brand p {
  margin: 0;
  color: var(--neutral-500);
  font-size: 0.9rem;
}

.logo {
  width: 48px;
  height: 48px;
  border-radius: 16px;
  background: linear-gradient(135deg, #4c6ef5, #60a5fa);
  display: grid;
  place-items: center;
  font-weight: 700;
  color: #fff;
  letter-spacing: 1px;
}

.nav {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.nav-item {
  color: var(--neutral-700);
  font-weight: 500;
  position: relative;
}

.nav-item::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -0.4rem;
  width: 100%;
  height: 2px;
  background: linear-gradient(135deg, #4c6ef5, #60a5fa);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.3s ease;
}

.nav-item:hover::after,
.nav-item:focus-visible::after {
  transform: scaleX(1);
}

.actions {
  display: flex;
  gap: 0.75rem;
  align-items: center;
}

.btn {
  border-radius: 999px;
  padding: 0.65rem 1.5rem;
  font-weight: 600;
  border: 1px solid transparent;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn.primary {
  background: linear-gradient(135deg, #4c6ef5, #2563eb);
  color: #fff;
  box-shadow: 0 10px 25px rgba(76, 110, 245, 0.35);
}

.btn.primary:hover {
  transform: translateY(-1px);
  box-shadow: 0 16px 30px rgba(76, 110, 245, 0.28);
}

.btn.ghost {
  background: transparent;
  border-color: rgba(76, 110, 245, 0.3);
  color: var(--neutral-700);
}

.btn.ghost:hover {
  border-color: rgba(76, 110, 245, 0.6);
}

@media (max-width: 960px) {
  .header {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .brand {
    justify-content: center;
  }

  .actions {
    justify-content: center;
  }
}
</style>
