<template>
  <section class="hero">
    <div class="hero-content">
      <p class="eyebrow">{{ eyebrow }}</p>
      <h2>{{ title }}</h2>
      <p class="subtitle">{{ subtitle }}</p>
      <div class="cta-group">
        <button class="btn primary">{{ primaryAction }}</button>
        <button class="btn ghost">{{ secondaryAction }}</button>
      </div>
      <div class="trusted">
        <span>已服务于</span>
        <ul>
          <li v-for="brand in brands" :key="brand">{{ brand }}</li>
        </ul>
      </div>
    </div>
    <div class="hero-visual">
      <div class="metric-card" v-for="metric in highlightedMetrics" :key="metric.label">
        <span class="label">{{ metric.label }}</span>
        <strong>{{ metric.value }}</strong>
        <span class="hint">{{ metric.hint }}</span>
      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  eyebrow: String,
  title: String,
  subtitle: String,
  primaryAction: String,
  secondaryAction: String,
  brands: {
    type: Array,
    default: () => [],
  },
  highlightedMetrics: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped>
.hero {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 3rem;
  align-items: center;
  padding: 4rem 0;
}

.eyebrow {
  text-transform: uppercase;
  letter-spacing: 0.24em;
  color: #4c6ef5;
  font-weight: 600;
  margin-bottom: 1rem;
}

.hero h2 {
  font-size: clamp(2.8rem, 5vw, 3.6rem);
  line-height: 1.1;
  margin: 0 0 1.5rem;
}

.subtitle {
  font-size: 1.1rem;
  color: var(--neutral-600);
  margin-bottom: 2.5rem;
  max-width: 34rem;
}

.cta-group {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-bottom: 2rem;
}

.btn {
  border-radius: 999px;
  padding: 0.85rem 2.4rem;
  font-weight: 600;
  border: 1px solid transparent;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn.primary {
  background: linear-gradient(135deg, #2563eb, #1d4ed8);
  color: #fff;
  box-shadow: 0 20px 35px rgba(37, 99, 235, 0.25);
}

.btn.ghost {
  background: transparent;
  border-color: rgba(37, 99, 235, 0.35);
  color: var(--neutral-700);
}

.trusted {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  align-items: center;
  color: var(--neutral-500);
}

.trusted ul {
  display: flex;
  gap: 1.25rem;
  list-style: none;
  padding: 0;
  margin: 0;
  color: var(--neutral-600);
  font-weight: 600;
}

.hero-visual {
  display: grid;
  gap: 1rem;
  justify-items: start;
}

.metric-card {
  background: linear-gradient(135deg, rgba(37, 99, 235, 0.1), rgba(37, 99, 235, 0.05));
  border: 1px solid rgba(37, 99, 235, 0.12);
  border-radius: 24px;
  padding: 1.5rem 2rem;
  min-width: 220px;
  box-shadow: 0 10px 30px rgba(15, 23, 42, 0.08);
}

.metric-card strong {
  display: block;
  font-size: 2.2rem;
  color: #1e293b;
  margin: 0.5rem 0;
}

.metric-card .label {
  font-size: 0.85rem;
  color: var(--neutral-500);
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

.metric-card .hint {
  color: var(--neutral-500);
  font-size: 0.85rem;
}

@media (max-width: 960px) {
  .hero {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .subtitle,
  .trusted {
    margin-left: auto;
    margin-right: auto;
    justify-content: center;
  }

  .hero-visual {
    justify-items: center;
  }
}
</style>
