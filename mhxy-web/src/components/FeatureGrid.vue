<template>
  <section class="feature-section">
    <header>
      <p class="eyebrow">{{ eyebrow }}</p>
      <h2>{{ title }}</h2>
      <p class="description">{{ description }}</p>
    </header>
    <div class="feature-grid">
      <article v-for="feature in features" :key="feature.title" class="feature-card">
        <div class="icon">{{ feature.icon }}</div>
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.summary }}</p>
        <ul>
          <li v-for="item in feature.items" :key="item">{{ item }}</li>
        </ul>
      </article>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  eyebrow: String,
  title: String,
  description: String,
  features: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped>
.feature-section {
  padding: 4rem 0 2rem;
  display: grid;
  gap: 2.5rem;
}

header {
  text-align: center;
  max-width: 640px;
  margin: 0 auto;
}

header h2 {
  font-size: 2.2rem;
  margin-bottom: 1rem;
}

header .description {
  color: var(--neutral-600);
  margin: 0;
  line-height: 1.7;
}

.eyebrow {
  text-transform: uppercase;
  color: #2563eb;
  letter-spacing: 0.24em;
  margin-bottom: 0.75rem;
  font-weight: 600;
}

.feature-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.8rem;
}

.feature-card {
  padding: 2rem;
  background: #fff;
  border-radius: 24px;
  border: 1px solid rgba(148, 163, 184, 0.2);
  box-shadow: 0 24px 36px rgba(15, 23, 42, 0.08);
  display: grid;
  gap: 1rem;
  text-align: left;
}

.feature-card h3 {
  margin: 0;
}

.feature-card p {
  margin: 0;
  color: var(--neutral-600);
}

.feature-card ul {
  margin: 0;
  padding-left: 1.1rem;
  color: var(--neutral-500);
  line-height: 1.6;
}

.icon {
  width: 48px;
  height: 48px;
  border-radius: 16px;
  background: rgba(37, 99, 235, 0.12);
  color: #2563eb;
  display: grid;
  place-items: center;
  font-size: 1.4rem;
  font-weight: 700;
}
</style>
