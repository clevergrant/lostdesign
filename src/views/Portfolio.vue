<template>
  <div id="portfolio">
    <h1>My Portfolio</h1>
    <p class="subtitle">Check out my recent work and other sites</p>

    <div class="portfolio-grid">
      <div class="portfolio-item">
        <div class="portfolio-layout">
          <img
            src="/img/fireemblem-screenshot.png"
            alt="Fire Emblem Codebreaker Screenshot"
            class="portfolio-image"
          />
          <div class="portfolio-content">
            <h2>Fire Emblem Codebreaker</h2>
            <p>
              A code generation site that provides Codebreaker codes for the
              original Fire Emblem games. Select desired cheats and get
              ready-to-use codes.
            </p>
            <div class="tags">
              <span class="tag">TypeScript</span>
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
            </div>
            <div class="links">
              <a
                href="https://fireemblem.lostdesign.dev/"
                target="_blank"
                class="visit-link"
                >Visit Site</a
              >
              <a
                href="https://github.com/clevergrant/fire-emblem"
                target="_blank"
                class="github-link"
              >
                <span>GitHub</span>
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class="portfolio-item">
        <div class="portfolio-layout">
          <img
            src="/img/skyrim-screenshot.png"
            alt="Skyrim Alchemy Screenshot"
            class="portfolio-image"
          />
          <div class="portfolio-content">
            <h2>Skyrim Alchemy</h2>
            <p>
              An interactive Skyrim alchemy project to discover potion
              combinations and ingredient effects.
            </p>
            <div class="tags">
              <span class="tag">JavaScript</span>
              <span class="tag">Web App</span>
              <span class="tag">Gaming</span>
            </div>
            <div class="links">
              <a
                href="https://skyrim.lostdesign.dev/"
                target="_blank"
                class="visit-link"
                >Visit Site</a
              >
              <a
                href="https://github.com/clevergrant/skyrim-new"
                target="_blank"
                class="github-link"
              >
                <span>GitHub</span>
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class="portfolio-item">
        <div class="portfolio-content">
          <h2>GitHub Projects</h2>
          <p>
            Browse my open-source contributions and personal projects on GitHub.
          </p>
          <div class="tags">
            <span class="tag">Open Source</span>
            <span class="tag">Collaboration</span>
            <span class="tag">Code</span>
          </div>
          <a
            href="https://github.com/clevergrant"
            target="_blank"
            class="visit-link"
            >Visit GitHub</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "PortfolioView",
});
</script>

<style scoped>
#portfolio {
  padding: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

h1 {
  color: var(--primary);
  margin-bottom: 0.5rem;
  font-size: 2.5rem;
}

.dark-theme h1 {
  color: #a7c1e0; /* Lighter color for headers in dark mode */
}

h2 {
  color: var(--primary);
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.dark-theme h2 {
  color: #a7c1e0; /* Lighter color for headers in dark mode */
}

.subtitle {
  color: var(--text);
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

.portfolio-grid {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.portfolio-item {
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: transform 0.2s ease, box-shadow 0.2s ease,
    background-color 0.3s ease;
  box-sizing: border-box;
}

.dark-theme .portfolio-item {
  background-color: var(--accent);
}

.portfolio-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
}

.portfolio-layout {
  display: flex;
  align-items: center;
}

.portfolio-content {
  padding: 25px;
  width: 70%;
  box-sizing: border-box;
}

.portfolio-content p {
  color: var(--text);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 1.5rem;
  gap: 8px;
}

.tag {
  background-color: #edf8ff;
  color: var(--primary);
  font-size: 0.8rem;
  padding: 4px 10px;
  border-radius: 15px;
  font-weight: 600;
}

.links {
  display: flex;
  gap: 12px;
}

.visit-link {
  display: inline-block;
  background-color: var(--primary);
  color: white;
  padding: 8px 16px;
  border-radius: 4px;
  text-decoration: none;
  font-weight: 600;
  transition: background-color 0.2s ease;
}

.visit-link:hover {
  background-color: #3a547a;
}

.github-link {
  display: inline-block;
  background-color: #333;
  color: white;
  padding: 8px 16px;
  border-radius: 4px;
  text-decoration: none;
  font-weight: 600;
  transition: background-color 0.2s ease;
}

.github-link:hover {
  background-color: #555;
}

.portfolio-image {
  width: 30%;
  height: auto;
  object-fit: cover;
  border-radius: 4px;
  margin-right: 15px;
  padding: 15px;
  flex-shrink: 0;
}

@media (max-width: 768px) {
  #portfolio {
    padding: 15px;
  }

  .portfolio-layout {
    flex-direction: column;
  }

  .portfolio-image {
    width: 100%;
    height: 150px;
    margin-bottom: 15px;
    margin-right: 0;
    padding: 10px;
  }

  .portfolio-content {
    width: 100%;
    padding: 15px;
  }

  .portfolio-item {
    padding: 0 0 10px 0;
  }
}

@media (max-width: 480px) {
  h1 {
    font-size: 2rem;
  }

  .subtitle {
    font-size: 1rem;
  }

  .portfolio-item {
    margin-bottom: 20px;
    padding: 0 0 10px 0;
  }

  .portfolio-content {
    padding: 15px;
  }

  .portfolio-image {
    height: 120px;
    padding: 15px;
  }

  .tags {
    margin-bottom: 1rem;
  }

  .links {
    flex-direction: column;
    gap: 8px;
  }

  .visit-link,
  .github-link {
    width: 100%;
    text-align: center;
  }
}
</style>
