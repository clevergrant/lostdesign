<template>
  <div id="home">
    <h1>Welcome to Lost Design</h1>
    <p>Creative web development & design solutions</p>
    <div class="cta-buttons">
      <router-link to="/portfolio" class="btn primary"
        >View Portfolio</router-link
      >
      <router-link to="/about" class="btn secondary">About Me</router-link>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomePage",
});
</script>

<style scoped>
#home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  text-align: center;
  padding: 0 20px;
}

h1 {
  color: var(--primary);
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

p {
  color: var(--text);
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

.cta-buttons {
  display: flex;
  gap: 15px;
}

.btn {
  padding: 10px 20px;
  border-radius: 4px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.2s ease;
}

.btn.primary {
  background-color: var(--primary);
  color: white;
}

.btn.primary:hover {
  background-color: #3a547a;
}

.btn.secondary {
  background-color: var(--secondary);
  color: #303c4a;
}

.btn.secondary:hover {
  background-color: #d6b98c;
}

/* Mobile responsiveness */
@media screen and (max-width: 768px) {
  #home {
    padding-top: 30px;
    padding-bottom: 30px;
  }
}

@media screen and (max-width: 480px) {
  h1 {
    font-size: 2rem;
  }

  p {
    font-size: 1rem;
  }

  .cta-buttons {
    flex-direction: column;
    width: 100%;
    max-width: 250px;
  }

  .btn {
    width: 100%;
    text-align: center;
  }
}
</style>
