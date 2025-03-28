<template>
  <div id="about">
    <h1>Grant Perdue</h1>
    <p class="subtitle">
      Full-Stack Developer | South San Francisco, CA | (760) 712-2617 |
      grantmperdue@gmail.com
    </p>

    <div class="about-content">
      <section class="resume-section">
        <h2>Professional Summary</h2>
        <p>
          Accomplished Full-Stack Developer with 9+ years of experience
          delivering robust web applications with a commitment to code quality
          and thoughtful architecture. Specializes in React/TypeScript
          development with proven success building features used by millions of
          users. Combines technical expertise with a disciplined approach that
          prioritizes sustainable solutions over quick fixes.
        </p>
      </section>

      <section class="resume-section">
        <h2>Technical Expertise</h2>
        <div class="skills">
          <div class="skill-group">
            <h3>Frontend</h3>
            <p>
              JavaScript/TypeScript, React.js, Redux.js, Vue.js, HTML5, CSS3,
              ES6+, Web/Service Workers, IndexedDB
            </p>
          </div>
          <div class="skill-group">
            <h3>Backend</h3>
            <p>
              Node.js, .NET Core (C#), MVC 5, Razor, Entity Framework 6, PHP,
              ASP.NET
            </p>
          </div>
          <div class="skill-group">
            <h3>DevOps</h3>
            <p>
              Git, GitHub, Jenkins, Docker, CI/CD, AWS Services, Azure Cloud,
              New Relic, Splunk
            </p>
          </div>
          <div class="skill-group">
            <h3>Additional</h3>
            <p>
              Java, Python, MongoDB, Functional Programming (Julia, Lisp,
              Elixir), Agile/JIRA, UX Design
            </p>
          </div>
        </div>
      </section>

      <section class="resume-section">
        <h2>Professional Experience</h2>

        <div class="job">
          <div class="job-header">
            <h3>Adobe — Software Engineer - Full Stack</h3>
            <p class="job-location">San Jose, CA | March 2021 - August 2024</p>
          </div>
          <ul>
            <li>
              Engineered hyper-personalized UI components used by millions of
              users daily in one of Adobe's most visible products
            </li>
            <li>
              Created and implemented a portal for Adobe employees to interact
              with AWS services for AI tools, showcasing extensive AWS API
              integration
            </li>
            <li>
              Pioneered advanced browser technologies ensuring consistent
              analytics flows and improved performance
            </li>
            <li>
              Championed software patterns that reduced code duplication,
              leading to higher quality, more maintainable codebase
            </li>
            <li>
              Applied rigorous approach to development, prioritizing proper
              implementation over quick fixes that could compromise quality
            </li>
          </ul>
        </div>

        <div class="job">
          <div class="job-header">
            <h3>Sponsr — Senior Full Stack Developer</h3>
            <p class="job-location">Sandy, UT | July 2020 - March 2021</p>
          </div>
          <ul>
            <li>
              Architected React.js rewrite of proprietary application,
              delivering improved functionality and user experience
            </li>
            <li>
              Created an innovative React-like framework for PHP, successfully
              modernizing legacy application while maintaining compatibility
            </li>
          </ul>
        </div>

        <div class="job">
          <div class="job-header">
            <h3>Brigham Young University — Software Developer</h3>
            <p class="job-location">Provo, UT | October 2018 - April 2020</p>
          </div>
          <ul>
            <li>
              Led frontend development for media management system supporting
              20,000+ users
            </li>
            <li>
              Designed robust infrastructure enhancing system reliability and
              performance under high-volume usage
            </li>
            <li>
              Architected layered code structure with Data Access and Service
              layers, simplifying testing and bug management
            </li>
          </ul>
        </div>

        <div class="job">
          <div class="job-header">
            <h3>Brigham Young University — Web Developer</h3>
            <p class="job-location">Provo, UT | February 2015 - April 2017</p>
          </div>
          <ul>
            <li>
              Developed CMS enabling 200+ faculty members and research teams to
              self-manage website content
            </li>
            <li>
              Implemented ASP.NET MVC framework with modern features, ensuring
              long-term maintainability
            </li>
            <li>
              Established client relationships through consultations, providing
              tailored solutions to varied stakeholder needs
            </li>
          </ul>
        </div>
      </section>

      <section class="resume-section">
        <h2>Education</h2>
        <div class="education">
          <h3>
            Brigham Young University — B.S. Information Technology | April 2020
          </h3>
          <ul>
            <li>
              Completed Computer Science Minor with coursework in Software
              Architecture, Data Structures, Algorithms
            </li>
            <li>Advanced coursework in UX Design, Web/App Development</li>
            <li>
              Substantial coursework toward Business Management Minor | UX
              Design Club Member
            </li>
          </ul>
        </div>
      </section>

      <section class="resume-section">
        <h2>Key Projects</h2>

        <div class="project">
          <h3>
            Microsoft Azure Open-Source Team — Capstone Project | 2019-2020
          </h3>
          <ul>
            <li>
              Developed data aggregation dashboard for cloud-native applications
              for official open-source repository
            </li>
            <li>
              Served as primary frontend developer throughout project lifecycle,
              coordinating team workloads
            </li>
          </ul>
        </div>

        <div class="project">
          <h3>Web Technologies Course Curriculum Redesign | 2019-2020</h3>
          <ul>
            <li>
              Completely rewrote the labs for the beginners web development
              course for the Information Technology major
            </li>
            <li>
              Designed new curriculum incorporating diverse technology stack
              (Docker, HTML/CSS/JavaScript, .NET Core, MongoDB, Azure, Node.js)
            </li>
            <li>
              Created comprehensive documentation; curriculum approved and
              implemented university-wide
            </li>
          </ul>
        </div>
      </section>

      <section class="resume-section">
        <h2>Languages</h2>
        <p>English (Native), French (Professional)</p>
      </section>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AboutView",
});
</script>

<style scoped>
#about {
  padding: 20px;
  max-width: 900px;
  margin: 0 auto;
  line-height: 1.6;
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
  margin-top: 1.5rem;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid var(--accent);
}

.dark-theme h2 {
  color: #a7c1e0; /* Lighter color for headers in dark mode */
}

h3 {
  color: var(--text);
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.dark-theme h3 {
  color: #e6c89c; /* Keep the "about me" text dark in dark mode */
}

.subtitle {
  color: var(--text);
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

.about-content {
  background-color: white;
  border-radius: 8px;
  padding: 30px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: background-color 0.3s ease;
}

.dark-theme .about-content {
  background-color: var(--accent);
}

.resume-section {
  margin-bottom: 2rem;
}

.skills {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}

.skill-group h3 {
  margin-bottom: 0.5rem;
  color: var(--primary);
}

.job {
  margin-bottom: 1.5rem;
}

.job-header {
  margin-bottom: 0.5rem;
}

.job-location {
  font-style: italic;
  color: var(--text);
  opacity: 0.8;
  margin-top: -0.5rem;
}

ul {
  padding-left: 1.5rem;
  margin-top: 0.5rem;
}

li {
  margin-bottom: 0.5rem;
}

.project {
  margin-bottom: 1.5rem;
}

@media (max-width: 768px) {
  .skills {
    grid-template-columns: 1fr;
  }

  #about {
    padding: 15px;
  }
}
</style>
