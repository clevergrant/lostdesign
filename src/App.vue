<template>
  <div id="app">
    <div id="logo-space">
      <svg
        id="logo"
        viewBox="120.055 86.526 260.074 326.59"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:bx="https://boxy-svg.com"
      >
        <defs>
          <bx:grid x="120.055" y="86.526" width="260.074" height="326.59" />
        </defs>
        <path
          d="M 790.4 423.2 m -129.003 0 a 129.003 129.003 0 1 0 258.006 0 a 129.003 129.003 0 1 0 -258.006 0 Z M 790.4 423.2 m -64.501 0 a 64.501 64.501 0 0 1 129.002 0 a 64.501 64.501 0 0 1 -129.002 0 Z"
          style=""
          transform="matrix(1, 0.000079, -0.000079, 1, -540.366392, -139.864531)"
          bx:shape="ring 790.4 423.2 64.501 64.501 129.003 129.003 1@68f4b763"
        />
        <rect
          x="120.987"
          y="87.5"
          width="64.643"
          height="325"
          rx="32.3"
          ry="32.3"
        />
        <rect
          x="314.37"
          y="87.5"
          width="64.643"
          height="325"
          rx="32.3"
          ry="32.3"
        />
        <circle ref="eyeball" id="eyeball" cx="250" cy="283.379" r="30" />
      </svg>
      <h1>lost design</h1>
    </div>
    <div id="main">
      <nav>
        <router-link to="/">Home</router-link>
        <router-link to="/portfolio">Portfolio</router-link>
        <router-link to="/about">About</router-link>
      </nav>
      <router-view />
    </div>
    <ThemeToggle />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted, onUnmounted } from "vue";
import { distance } from "@/util";
import ThemeToggle from "@/components/ThemeToggle.vue";

export default defineComponent({
  name: "App",
  components: {
    ThemeToggle,
  },
  setup() {
    const eyeball = ref<SVGCircleElement | null>(null);

    const moveEyeball = (e: MouseEvent) => {
      if (!eyeball.value) return;
      const rect = eyeball.value.getBoundingClientRect() as DOMRect;
      if (!rect) return;

      const x = rect.x + 36.74 / 2;
      const y = rect.y + 36.74 / 2;

      const stretchLimit = 250;

      const absDist = distance(e.x, e.y, x, y);
      const percentDist =
        (absDist > stretchLimit ? stretchLimit : absDist) / stretchLimit;

      const yOffset = percentDist * 30;

      const radian = Math.atan2(e.pageX - x, e.pageY - y);
      const deg = radian * (180 / Math.PI) * -1;

      const xOrigin = eyeball.value.cx.baseVal.value;
      const yOrigin = eyeball.value.cy.baseVal.value;

      const transformAttr = `translate(0,${yOffset}) rotate(${deg}, ${xOrigin}, ${
        yOrigin - yOffset
      })`;
      eyeball.value.setAttribute("transform", transformAttr);
    };

    onMounted(() => {
      addEventListener("mousemove", moveEyeball);
    });

    onUnmounted(() => {
      removeEventListener("mousemove", moveEyeball);
    });

    return {
      eyeball,
    };
  },
});
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Nunito:300,400,700&display=swap");

:root {
  font-family: "Nunito", sans-serif;
  --primary: #4b6a97;
  /* Improved blue - more muted and professional */
  --secondary: #e6c89c;
  /* Warmer tan color */
  --accent: #edf8ff;
  /* Light blue for accents */
  --text: #303c4a;
  /* Darker text for better readability */
  --background: #f5f8fb;
  /* Very light background */
}

:root.dark-theme {
  --primary: #345380;
  /* Darker blue for dark mode */
  --secondary: #d9b37d;
  /* Slightly darker tan for contrast */
  --accent: #1e2a3a;
  /* Dark blue accent */
  --text: #e0e6ed;
  /* Light text for dark mode */
  --background: #1a212c;
  /* Dark background */
}

body {
  margin: 0;
  background-color: var(--primary);
  color: var(--text);
  transition: background-color 0.3s ease, color 0.3s ease;
}

#app {
  display: flex;
  height: 100vh;
  width: 100vw;
  overflow-x: hidden;
}

#app > div {
  flex: 1;
}

#logo-space {
  flex: 0.3 !important;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: var(--primary);
  transition: background-color 0.3s ease;
}

#logo-space > h1 {
  color: #edf8ff;
  letter-spacing: 1px;
  margin-top: 20px;
}

#logo {
  height: 200px;
  fill: var(--secondary);
}

#eyeball {
  transition: fill 0.5s;
  fill: #edf8ff;
}

#eyeball:hover {
  fill: white;
}

#main {
  flex: 0.7 !important;
  background-color: var(--background);
  padding: 20px;
  display: flex;
  flex-direction: column;
  overflow-y: auto;
  transition: background-color 0.3s ease;
}

nav {
  display: flex;
  gap: 20px;
  margin-bottom: 30px;
}

nav a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 600;
  position: relative;
  padding: 5px 0;
  transition: color 0.3s ease;
}

.dark-theme nav a {
  color: #a7c1e0; /* Lighter color for tab names in dark mode */
}

nav a::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--primary);
  transition: width 0.3s;
}

nav a:hover::after,
nav a.router-link-active::after {
  width: 100%;
}

/* Media Queries for responsive design */
@media screen and (max-width: 768px) {
  #app {
    flex-direction: column;
    height: auto;
    min-height: 100vh;
  }

  #logo-space {
    flex: initial !important;
    padding: 20px 0;
  }

  #logo {
    height: 150px;
  }

  #main {
    flex: initial !important;
  }

  nav {
    flex-wrap: wrap;
  }
}

@media screen and (max-width: 480px) {
  #logo {
    height: 120px;
  }

  #logo-space > h1 {
    font-size: 1.5rem;
  }

  nav {
    justify-content: center;
  }

  #main {
    padding: 15px;
  }
}
</style>
