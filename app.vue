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
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/portfolio">Portfolio</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
      </nav>
      <NuxtPage />
    </div>
    <ThemeToggle />
  </div>
</template>

<script setup lang="ts">
import { distance } from "~/utils/distance";

useHead({
  titleTemplate: (title) =>
    title ? `${title} - Lost Design` : "Lost Design",
});

useSeoMeta({
  description:
    "Creative web development & design solutions by Grant Perdue",
  ogTitle: "Lost Design",
  ogDescription:
    "Creative web development & design solutions by Grant Perdue",
  ogType: "website",
});

const eyeball = ref<SVGCircleElement | null>(null);

const moveEyeball = (e: MouseEvent) => {
  if (!eyeball.value) return;
  const rect = eyeball.value.getBoundingClientRect();
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
</script>
