<template>
  <section class="stats">
    <article v-for="stat in stats" :key="stat.label" class="stat-card">
      <h3>{{ stat.value }}</h3>
      <p class="label">{{ stat.label }}</p>
      <p class="description">{{ stat.description }}</p>
    </article>
  </section>
</template>

<script setup>
const props = defineProps({
  stats: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped>
.stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  padding: 2rem 0 1rem;
}

.stat-card {
  padding: 2rem;
  background: linear-gradient(180deg, #ffffff 0%, #f8fbff 100%);
  border-radius: 24px;
  border: 1px solid rgba(148, 163, 184, 0.2);
  box-shadow: 0 20px 35px rgba(15, 23, 42, 0.06);
}

.stat-card h3 {
  font-size: 2.4rem;
  margin: 0 0 0.75rem;
  color: #0f172a;
}

.label {
  font-weight: 600;
  color: var(--neutral-600);
  margin-bottom: 0.5rem;
}

.description {
  margin: 0;
  color: var(--neutral-500);
  line-height: 1.6;
}
</style>
