<template>
  <section class="contact">
    <div>
      <h2>{{ title }}</h2>
      <p>{{ description }}</p>
    </div>
    <form class="contact-form">
      <input type="email" :placeholder="placeholder" />
      <button type="button">{{ action }}</button>
    </form>
  </section>
</template>

<script setup>
const props = defineProps({
  title: String,
  description: String,
  placeholder: {
    type: String,
    default: '请输入企业邮箱'
  },
  action: {
    type: String,
    default: '预约顾问'
  }
});
</script>

<style scoped>
.contact {
  margin: 5rem 0 2rem;
  padding: 3rem;
  border-radius: 28px;
  background: linear-gradient(135deg, rgba(14, 165, 233, 0.12), rgba(37, 99, 235, 0.15));
  border: 1px solid rgba(37, 99, 235, 0.2);
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  align-items: center;
  justify-content: space-between;
}

.contact h2 {
  margin: 0 0 0.75rem;
  font-size: 2rem;
}

.contact p {
  margin: 0;
  color: var(--neutral-600);
  max-width: 420px;
}

.contact-form {
  display: flex;
  gap: 0.75rem;
  flex-wrap: wrap;
}

.contact-form input {
  padding: 0.85rem 1.2rem;
  border-radius: 999px;
  border: 1px solid rgba(37, 99, 235, 0.4);
  min-width: 240px;
  font-size: 1rem;
}

.contact-form button {
  padding: 0.85rem 2rem;
  border-radius: 999px;
  border: none;
  background: linear-gradient(135deg, #2563eb, #1d4ed8);
  color: #fff;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 16px 30px rgba(37, 99, 235, 0.22);
}

@media (max-width: 720px) {
  .contact {
    text-align: center;
    justify-content: center;
  }

  .contact p {
    margin: 0 auto;
  }

  .contact-form {
    justify-content: center;
  }
}
</style>
