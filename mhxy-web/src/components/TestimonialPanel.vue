<template>
  <section class="testimonial">
    <article>
      <p class="quote">“{{ quote }}”</p>
      <footer>
        <div>
          <strong>{{ author.name }}</strong>
          <span>{{ author.title }}</span>
        </div>
        <img :src="author.logo" :alt="author.name" v-if="author.logo" />
      </footer>
    </article>
  </section>
</template>

<script setup>
const props = defineProps({
  quote: String,
  author: {
    type: Object,
    default: () => ({})
  },
});
</script>

<style scoped>
.testimonial {
  padding: 4rem 0;
}

article {
  background: linear-gradient(135deg, #0f172a, #1d4ed8);
  color: #f8fafc;
  padding: 3rem;
  border-radius: 32px;
  display: grid;
  gap: 2rem;
  position: relative;
  overflow: hidden;
}

article::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at top right, rgba(148, 163, 255, 0.35), transparent 55%);
}

.quote {
  font-size: 1.6rem;
  line-height: 1.6;
  margin: 0;
  position: relative;
  z-index: 1;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  z-index: 1;
}

footer strong {
  display: block;
  font-size: 1rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

footer span {
  color: rgba(226, 232, 240, 0.85);
  font-size: 0.95rem;
}

footer img {
  height: 36px;
  filter: brightness(1.15);
}
</style>
