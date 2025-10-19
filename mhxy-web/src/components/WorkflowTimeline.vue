<template>
  <section class="timeline">
    <header>
      <h2>{{ title }}</h2>
      <p>{{ description }}</p>
    </header>
    <ol>
      <li v-for="step in steps" :key="step.title">
        <div class="step-number">{{ step.number }}</div>
        <div class="step-content">
          <h3>{{ step.title }}</h3>
          <p>{{ step.detail }}</p>
          <span>{{ step.duration }}</span>
        </div>
      </li>
    </ol>
  </section>
</template>

<script setup>
const props = defineProps({
  title: String,
  description: String,
  steps: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped>
.timeline {
  padding: 4rem 0;
  display: grid;
  gap: 2rem;
}

header {
  max-width: 620px;
  text-align: left;
}

header h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

header p {
  margin: 0;
  color: var(--neutral-600);
}

ol {
  list-style: none;
  margin: 0;
  padding: 0;
  display: grid;
  gap: 1.5rem;
}

li {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 1.5rem;
  align-items: start;
  padding: 2rem;
  background: #fff;
  border-radius: 24px;
  border: 1px solid rgba(226, 232, 240, 0.8);
  box-shadow: 0 20px 35px rgba(15, 23, 42, 0.08);
}

.step-number {
  width: 52px;
  height: 52px;
  border-radius: 18px;
  background: linear-gradient(135deg, #60a5fa, #2563eb);
  color: #fff;
  display: grid;
  place-items: center;
  font-weight: 700;
  font-size: 1.1rem;
}

.step-content h3 {
  margin: 0 0 0.5rem;
}

.step-content p {
  margin: 0 0 0.75rem;
  color: var(--neutral-600);
}

.step-content span {
  font-size: 0.85rem;
  color: var(--neutral-500);
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

@media (max-width: 720px) {
  li {
    grid-template-columns: 1fr;
  }

  .step-number {
    justify-self: start;
  }
}
</style>
