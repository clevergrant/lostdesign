<template>
  <button
    @click="toggleTheme"
    class="theme-toggle"
    :class="{ 'dark-mode': isDarkMode }"
    aria-label="Toggle dark/light mode"
  >
    <svg
      v-if="isDarkMode"
      xmlns="http://www.w3.org/2000/svg"
      width="20"
      height="20"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <circle cx="12" cy="12" r="5"></circle>
      <line x1="12" y1="1" x2="12" y2="3"></line>
      <line x1="12" y1="21" x2="12" y2="23"></line>
      <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
      <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
      <line x1="1" y1="12" x2="3" y2="12"></line>
      <line x1="21" y1="12" x2="23" y2="12"></line>
      <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
      <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
    </svg>
    <svg
      v-else
      xmlns="http://www.w3.org/2000/svg"
      width="20"
      height="20"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
    </svg>
  </button>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from "vue";

export default defineComponent({
  name: "ThemeToggle",
  setup() {
    const isDarkMode = ref(false);

    // Check for saved theme preference or prefers-color-scheme
    onMounted(() => {
      const savedTheme = localStorage.getItem("theme");
      if (savedTheme === "dark") {
        isDarkMode.value = true;
        document.documentElement.classList.add("dark-theme");
      } else if (savedTheme === "light") {
        isDarkMode.value = false;
      } else if (
        window.matchMedia &&
        window.matchMedia("(prefers-color-scheme: dark)").matches
      ) {
        isDarkMode.value = true;
        document.documentElement.classList.add("dark-theme");
      }
    });

    const toggleTheme = () => {
      isDarkMode.value = !isDarkMode.value;

      if (isDarkMode.value) {
        document.documentElement.classList.add("dark-theme");
        localStorage.setItem("theme", "dark");
      } else {
        document.documentElement.classList.remove("dark-theme");
        localStorage.setItem("theme", "light");
      }
    };

    return {
      isDarkMode,
      toggleTheme,
    };
  },
});
</script>

<style>
.theme-toggle {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--primary);
  color: var(--accent);
  border: none;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  transition: background-color 0.3s, transform 0.2s;
}

.theme-toggle:hover {
  transform: scale(1.05);
}

.theme-toggle.dark-mode {
  background-color: var(--secondary);
  color: var(--primary);
}

@media screen and (max-width: 768px) {
  .theme-toggle {
    bottom: 15px;
    right: 15px;
  }
}

@media screen and (max-width: 480px) {
  .theme-toggle {
    width: 40px;
    height: 40px;
    bottom: 10px;
    right: 10px;
  }
}
</style>
