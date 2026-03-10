<template>
  <div class="portfolio-root">
    <!-- ═══════════ HEADER ═══════════ -->
    <header class="site-header" :class="{ scrolled: scrolled }">
      <div class="header-inner">
        <div class="brand">
          <div class="brand-avatar">S</div>
          <div>
            <p class="brand-domain">sanakulov.uz</p>
            <p class="brand-name">Anvar Sanakulov</p>
          </div>
        </div>

        <nav class="desktop-nav">
          <a href="#hero">Home</a>
          <a href="#about">About</a>
          <a href="#skills">Skills</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </nav>

        <div class="header-actions">
          <button class="btn-resume" @click="openResume">
            <svg
              width="14"
              height="14"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2.5"
            >
              <path
                d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"
              />
              <polyline points="14 2 14 8 20 8" />
            </svg>
            Resume
          </button>
          <a class="btn-hire" href="#contact">Hire Me</a>
          <button
            class="burger"
            @click="mobileOpen = !mobileOpen"
            aria-label="menu"
          >
            <span :class="{ open: mobileOpen }"></span>
          </button>
        </div>
      </div>

      <!-- Mobile Nav -->
      <div class="mobile-nav" :class="{ open: mobileOpen }">
        <a href="#hero" @click="mobileOpen = false">Home</a>
        <a href="#about" @click="mobileOpen = false">About</a>
        <a href="#skills" @click="mobileOpen = false">Skills</a>
        <a href="#projects" @click="mobileOpen = false">Projects</a>
        <a href="#contact" @click="mobileOpen = false">Contact</a>
        <button
          class="btn-resume mobile"
          @click="
            openResume;
            mobileOpen = false;
          "
        >
          View Resume (PDF)
        </button>
      </div>
    </header>

    <main>
      <!-- ═══════════ HERO ═══════════ -->
      <section id="hero" class="hero-section">
        <div class="hero-bg-glow"></div>
        <div class="hero-content">
          <div class="hero-text" data-aos>
            <span class="tag">Backend Developer</span>
            <h1>
              Salom, I'm<br />
              <span class="gradient-text">Anvar Sanakulov.</span>
            </h1>
            <p class="hero-desc">
              25-year-old backend developer at <strong>BTS EXPRESS</strong>. I
              build clean APIs, scalable infrastructure, and deliver fast — with
              PHP, PostgreSQL, and Linux.
            </p>
            <div class="hero-btns">
              <a class="btn-primary" href="#projects">View Projects</a>
              <a class="btn-outline" href="#about">About Me</a>
            </div>
            <div class="hero-stats">
              <div class="stat">
                <span class="stat-num">3+</span><span>Years Exp.</span>
              </div>
              <div class="stat-divider"></div>
              <div class="stat">
                <span class="stat-num">10+</span><span>Projects</span>
              </div>
              <div class="stat-divider"></div>
              <div class="stat">
                <span class="stat-num">5+</span><span>Live Products</span>
              </div>
            </div>
          </div>
          <div class="hero-image-wrap">
            <div class="hero-glow-ring"></div>
            <div class="hero-avatar">
              <img :src="profileImage" alt="Anvar Sanakulov" />
            </div>
            <div class="availability-badge">
              <span class="pulse-dot"></span> Open to new projects
            </div>
          </div>
        </div>
      </section>

      <!-- ═══════════ ABOUT ═══════════ -->
      <section id="about" class="section">
        <div class="section-inner">
          <div class="section-label">About</div>
          <div class="about-grid">
            <div class="about-left">
              <h2 class="section-title">Building with purpose.</h2>
              <p class="section-body">
                I'm based in Uzbekistan and currently crafting backend solutions
                at BTS EXPRESS. I'm passionate about clean architecture,
                reliable systems, and continuous learning.
              </p>
              <p class="section-body">
                My education spans
                <strong
                  >Tashkent University of Information Technologies
                  (TUIT)</strong
                >
                and the <strong>System Design</strong> program at 42.uz.
              </p>
              <div class="about-tags">
                <span>PHP (Yii2)</span>
                <span>PostgreSQL</span>
                <span>Linux / Docker</span>
                <span>REST APIs</span>
              </div>
            </div>
            <div class="about-card">
              <h3>Highlights</h3>
              <ul>
                <li>
                  <span class="dot"></span>
                  <div>
                    <strong>Backend Developer</strong> — BTS EXPRESS (2023 –
                    present)
                  </div>
                </li>
                <li>
                  <span class="dot"></span>
                  <div><strong>System Design</strong> — 42.uz</div>
                </li>
                <li>
                  <span class="dot"></span>
                  <div>
                    <strong>B.S. Information Technologies</strong> — TUIT
                  </div>
                </li>
                <li>
                  <span class="dot"></span>
                  <div>Delivered 5+ production‑grade web applications</div>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- ═══════════ SKILLS ═══════════ -->
      <section id="skills" class="section dark-section">
        <div class="section-inner">
          <div class="section-label">Skills</div>
          <h2 class="section-title">Tech stack</h2>
          <p class="section-body">
            Expert in backend foundations with a focus on performance and
            reliability.
          </p>
          <div class="skills-grid">
            <div
              class="skill-card"
              v-for="group in skillGroups"
              :key="group.title"
            >
              <div class="skill-card-header">
                <span class="skill-icon" v-html="group.icon"></span>
                <h3>{{ group.title }}</h3>
              </div>
              <div class="skill-pills">
                <span v-for="s in group.items" :key="s" class="skill-pill">{{
                  s
                }}</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- ═══════════ PROJECTS ═══════════ -->
      <section id="projects" class="section">
        <div class="section-inner">
          <div class="section-label">Projects</div>
          <h2 class="section-title">Live Products</h2>
          <p class="section-body">
            Production-grade systems I've built and currently maintain.
          </p>

          <div class="projects-grid">
            <div class="project-card" v-for="p in projects" :key="p.url">
              <div class="project-header">
                <div class="project-icon-wrap">
                  <span v-html="p.icon"></span>
                </div>
                <div class="project-status">
                  <span class="live-dot"></span> Live
                </div>
              </div>
              <h3 class="project-title">{{ p.name }}</h3>
              <p class="project-url">{{ p.url }}</p>
              <p class="project-desc">{{ p.desc }}</p>
              <div class="project-tech">
                <span v-for="t in p.tech" :key="t">{{ t }}</span>
              </div>
              <a
                :href="'https://' + p.url"
                target="_blank"
                rel="noopener"
                class="project-link"
              >
                Visit site
                <svg
                  width="14"
                  height="14"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2.5"
                  stroke-linecap="round"
                >
                  <line x1="7" y1="17" x2="17" y2="7" />
                  <polyline points="7 7 17 7 17 17" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- ═══════════ FOOTER / CONTACT ═══════════ -->
    <footer id="contact" class="contact-footer">
      <div class="footer-glow"></div>
      <div class="footer-inner">
        <p class="section-label" style="justify-content: center; display: flex">
          Contact
        </p>
        <h2 class="footer-title">Let's work together.</h2>
        <p class="footer-desc">
          Loyihalar yoki hamkorlik bo'yicha gaplashmoqchimisiz?<br />
          Menga Telegram orqali yozing yoki kodlarimni GitHubda ko'ring.
        </p>

        <div class="contact-links">
          <a
            href="https://github.com/SanakulovDev"
            target="_blank"
            class="contact-card"
          >
            <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
              <path
                fill-rule="evenodd"
                d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
                clip-rule="evenodd"
              />
            </svg>
            <span>GitHub</span>
            <small>SanakulovDev</small>
          </a>
          <a
            href="https://t.me/Sanakulov_dev"
            target="_blank"
            class="contact-card telegram"
          >
            <svg width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.638z"
              />
            </svg>
            <span>Telegram</span>
            <small>@Sanakulov_dev</small>
          </a>
          <button class="contact-card resume-card" @click="openResume">
            <svg
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
            >
              <path
                d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"
              />
              <polyline points="14 2 14 8 20 8" />
              <line x1="16" y1="13" x2="8" y2="13" />
              <line x1="16" y1="17" x2="8" y2="17" />
              <polyline points="10 9 9 9 8 9" />
            </svg>
            <span>Resume</span>
            <small>View PDF</small>
          </button>
        </div>

        <p class="footer-copy">© 2026 Anvar Sanakulov — Backend Developer</p>
      </div>
    </footer>

    <!-- ═══════════ PDF RESUME MODAL ═══════════ -->
    <transition name="modal">
      <div v-if="resumeOpen" class="modal-backdrop" @click.self="closeResume">
        <div class="modal-box">
          <div class="modal-header">
            <div class="modal-title">
              <svg
                width="18"
                height="18"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
              >
                <path
                  d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"
                />
                <polyline points="14 2 14 8 20 8" />
              </svg>
              Anvar Sanakulov — Resume
            </div>
            <div class="modal-actions">
              <a
                :href="resumePdfUrl"
                download="Anvar_Sanakulov_Resume.pdf"
                class="btn-download"
              >
                <svg
                  width="14"
                  height="14"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2.5"
                  stroke-linecap="round"
                >
                  <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
                  <polyline points="7 10 12 15 17 10" />
                  <line x1="12" y1="15" x2="12" y2="3" />
                </svg>
                Download
              </a>
              <button
                class="modal-close"
                @click="closeResume"
                aria-label="close"
              >
                <svg
                  width="20"
                  height="20"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                >
                  <line x1="18" y1="6" x2="6" y2="18" />
                  <line x1="6" y1="6" x2="18" y2="18" />
                </svg>
              </button>
            </div>
          </div>
          <div class="pdf-viewer-wrap">
            <iframe
              :src="resumePdfUrl + '#toolbar=0&navpanes=0'"
              class="pdf-iframe"
              title="Resume PDF"
            ></iframe>
            <!-- Fallback for mobile -->
            <div class="pdf-fallback">
              <p>PDF ko'rish uchun</p>
              <a
                :href="resumePdfUrl"
                target="_blank"
                class="btn-primary"
                style="display: inline-flex; align-items: center; gap: 6px"
              >
                <svg
                  width="14"
                  height="14"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2.5"
                >
                  <path
                    d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                  />
                  <polyline points="15 3 21 3 21 9" />
                  <line x1="10" y1="14" x2="21" y2="3" />
                </svg>
                Yangi tab da ochish
              </a>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import profileImage from "./profile.jpg";

// ─── State ───────────────────────────────────────────────
const scrolled = ref(false);
const mobileOpen = ref(false);
const resumeOpen = ref(false);
const resumePdfUrl = ref("/resume.pdf");

// ─── Scroll handler ───────────────────────────────────────
function onScroll() {
  scrolled.value = window.scrollY > 20;
}
onMounted(() => window.addEventListener("scroll", onScroll));
onUnmounted(() => window.removeEventListener("scroll", onScroll));

// ─── Resume modal ─────────────────────────────────────────
function openResume() {
  resumeOpen.value = true;
  document.body.style.overflow = "hidden";
}
function closeResume() {
  resumeOpen.value = false;
  document.body.style.overflow = "";
}

// ─── Skills ───────────────────────────────────────────────
const skillGroups = [
  {
    title: "Backend",
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>`,
    items: ["PHP", "Yii2 Framework", "Laravel", "REST API"],
  },
  {
    title: "Database",
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><ellipse cx="12" cy="5" rx="9" ry="3"/><path d="M21 12c0 1.66-4 3-9 3s-9-1.34-9-3"/><path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5"/></svg>`,
    items: ["PostgreSQL", "MySQL", "Redis"],
  },
  {
    title: "Frontend",
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>`,
    items: ["HTML", "CSS", "JavaScript", "Vue.js"],
  },
  {
    title: "DevOps & Tools",
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><circle cx="12" cy="12" r="3"/><path d="M19.07 4.93a10 10 0 0 1 0 14.14M4.93 4.93a10 10 0 0 0 0 14.14"/></svg>`,
    items: ["Linux", "Docker", "Nginx", "Git", "SSH"],
  },
];

// ─── Projects ─────────────────────────────────────────────
const projects = [
  {
    name: "Tikitak",
    url: "tikitak.uz",
    desc: "Online chipta sotish platformasi. Tadbirlar, konsertlar va boshqa voqealarga chipta olish uchun qulay xizmat.",
    tech: ["PHP", "Yii2", "PostgreSQL", "Redis"],
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"><path d="M2 9a3 3 0 0 1 0 6v2a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2v-2a3 3 0 0 1 0-6V7a2 2 0 0 0-2-2H4a2 2 0 0 0-2 2z"/><path d="M13 5v2"/><path d="M13 17v2"/><path d="M13 11v2"/></svg>`,
  },
  {
    name: "AgentUp",
    url: "agentup.uz",
    desc: "Ko'chmas mulk va agentlik boshqaruv tizimi. Agentlar va mijozlarni birlashtiruvchi platforma.",
    tech: ["PHP", "Yii2", "PostgreSQL", "Vue.js"],
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"><path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>`,
  },
  {
    name: "Elsu",
    url: "elsu.uz",
    desc: "O'quv platformasi va ta'lim boshqaruv tizimi. Kurslar, o'quvchilar va o'qituvchilar uchun yagona xizmat.",
    tech: ["PHP", "Yii2", "MySQL", "JavaScript"],
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>`,
  },
];
</script>

<style scoped>
/* ═══════════════════════════════════════════
   TOKENS
═══════════════════════════════════════════ */
:root {
  --bg: #060a14;
  --bg2: #0d1526;
  --surface: rgba(255, 255, 255, 0.04);
  --surface-hover: rgba(255, 255, 255, 0.08);
  --border: rgba(255, 255, 255, 0.08);
  --green: #34d399;
  --green2: #10b981;
  --text: #f1f5f9;
  --muted: #94a3b8;
  --radius: 20px;
  --transition: 0.25s ease;
}

/* ═══════════════════════════════════════════
   RESET / ROOT
═══════════════════════════════════════════ */
.portfolio-root {
  font-family:
    "Inter",
    system-ui,
    -apple-system,
    sans-serif;
  background: #060a14;
  color: #f1f5f9;
  min-height: 100vh;
  scroll-behavior: smooth;
}

/* ═══════════════════════════════════════════
   HEADER
═══════════════════════════════════════════ */
.site-header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: rgba(6, 10, 20, 0.7);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border-bottom: 1px solid transparent;
  transition:
    border-color 0.3s,
    background 0.3s;
}
.site-header.scrolled {
  background: rgba(6, 10, 20, 0.92);
  border-bottom-color: rgba(255, 255, 255, 0.07);
}
.header-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 14px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
}
.brand {
  display: flex;
  align-items: center;
  gap: 12px;
}
.brand-avatar {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--green2), #06b6d4);
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 16px;
  color: #060a14;
  flex-shrink: 0;
}
.brand-domain {
  font-size: 11px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--muted);
}
.brand-name {
  font-size: 15px;
  font-weight: 600;
  color: var(--text);
}

.desktop-nav {
  display: none;
  gap: 28px;
}
@media (min-width: 768px) {
  .desktop-nav {
    display: flex;
  }
}
.desktop-nav a {
  font-size: 13.5px;
  color: var(--muted);
  text-decoration: none;
  transition: color var(--transition);
  letter-spacing: 0.02em;
}
.desktop-nav a:hover {
  color: var(--text);
}

.header-actions {
  display: flex;
  align-items: center;
  gap: 10px;
}
.btn-resume {
  display: flex;
  align-items: center;
  gap: 6px;
  background: var(--surface);
  border: 1px solid var(--border);
  color: var(--text);
  padding: 8px 16px;
  border-radius: 30px;
  font-size: 12.5px;
  font-weight: 600;
  cursor: pointer;
  transition:
    background var(--transition),
    border-color var(--transition);
}
.btn-resume:hover {
  background: var(--surface-hover);
  border-color: rgba(255, 255, 255, 0.18);
}
.btn-hire {
  background: linear-gradient(135deg, var(--green2), #059669);
  color: #060a14;
  padding: 9px 20px;
  border-radius: 30px;
  font-size: 12.5px;
  font-weight: 700;
  text-decoration: none;
  letter-spacing: 0.07em;
  text-transform: uppercase;
  transition:
    opacity var(--transition),
    transform var(--transition);
}
.btn-hire:hover {
  opacity: 0.88;
  transform: translateY(-1px);
}

/* Burger */
.burger {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 36px;
  height: 36px;
  background: none;
  border: none;
  cursor: pointer;
  gap: 5px;
  padding: 4px;
}
@media (min-width: 768px) {
  .burger {
    display: none;
  }
}
.burger span,
.burger span::before,
.burger span::after {
  display: block;
  width: 22px;
  height: 2px;
  background: var(--text);
  border-radius: 2px;
  transition: 0.3s;
  position: relative;
}
.burger span::before,
.burger span::after {
  content: "";
  position: absolute;
}
.burger span::before {
  top: -6px;
}
.burger span::after {
  top: 6px;
}
.burger span.open {
  background: transparent;
}
.burger span.open::before {
  transform: rotate(45deg);
  top: 0;
}
.burger span.open::after {
  transform: rotate(-45deg);
  top: 0;
}

/* Mobile nav */
.mobile-nav {
  display: flex;
  flex-direction: column;
  gap: 4px;
  padding: 0 20px;
  max-height: 0;
  overflow: hidden;
  transition:
    max-height 0.35s ease,
    padding 0.35s ease;
}
.mobile-nav.open {
  max-height: 360px;
  padding: 12px 20px 18px;
}
.mobile-nav a {
  color: var(--muted);
  text-decoration: none;
  padding: 11px 0;
  font-size: 15px;
  border-bottom: 1px solid var(--border);
  transition: color var(--transition);
}
.mobile-nav a:hover {
  color: var(--text);
}
.btn-resume.mobile {
  margin-top: 10px;
  width: 100%;
  justify-content: center;
}

/* ═══════════════════════════════════════════
   HERO
═══════════════════════════════════════════ */
.hero-section {
  min-height: calc(100vh - 68px);
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding: 80px 24px 60px;
}
.hero-bg-glow {
  position: absolute;
  top: -200px;
  left: 50%;
  transform: translateX(-50%);
  width: 900px;
  height: 700px;
  background: radial-gradient(
    ellipse,
    rgba(52, 211, 153, 0.07) 0%,
    transparent 70%
  );
  pointer-events: none;
}
.hero-content {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr;
  gap: 48px;
  width: 100%;
  align-items: center;
}
@media (min-width: 768px) {
  .hero-content {
    grid-template-columns: 1.15fr 0.85fr;
  }
}

.hero-text {
  display: flex;
  flex-direction: column;
  gap: 22px;
}

.tag {
  display: inline-block;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--green);
  background: rgba(52, 211, 153, 0.1);
  border: 1px solid rgba(52, 211, 153, 0.25);
  padding: 6px 14px;
  border-radius: 20px;
  width: fit-content;
}

.hero-text h1 {
  font-size: clamp(2.4rem, 6vw, 3.8rem);
  font-weight: 800;
  line-height: 1.15;
  color: var(--text);
  margin: 0;
}
.gradient-text {
  background: linear-gradient(135deg, var(--green) 0%, #06b6d4 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-desc {
  font-size: 1.05rem;
  color: var(--muted);
  line-height: 1.7;
  max-width: 520px;
}

.hero-btns {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
}
.btn-primary {
  background: linear-gradient(135deg, var(--green2), #059669);
  color: #060a14;
  padding: 13px 28px;
  border-radius: 30px;
  font-size: 13px;
  font-weight: 700;
  text-decoration: none;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  transition:
    opacity var(--transition),
    transform var(--transition),
    box-shadow var(--transition);
  box-shadow: 0 4px 24px rgba(16, 185, 129, 0.25);
}
.btn-primary:hover {
  opacity: 0.9;
  transform: translateY(-2px);
  box-shadow: 0 8px 32px rgba(16, 185, 129, 0.35);
}
.btn-outline {
  background: transparent;
  color: var(--text);
  padding: 12px 28px;
  border-radius: 30px;
  font-size: 13px;
  font-weight: 600;
  text-decoration: none;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  border: 1px solid rgba(255, 255, 255, 0.18);
  transition:
    border-color var(--transition),
    background var(--transition);
}
.btn-outline:hover {
  border-color: rgba(255, 255, 255, 0.4);
  background: rgba(255, 255, 255, 0.05);
}

.hero-stats {
  display: flex;
  align-items: center;
  gap: 24px;
  padding-top: 8px;
}
.stat {
  display: flex;
  flex-direction: column;
  gap: 2px;
}
.stat-num {
  font-size: 1.7rem;
  font-weight: 800;
  color: var(--text);
}
.stat span:last-child {
  font-size: 12px;
  color: var(--muted);
}
.stat-divider {
  width: 1px;
  height: 36px;
  background: var(--border);
}

/* Hero image */
.hero-image-wrap {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}
.hero-glow-ring {
  position: absolute;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: radial-gradient(
    circle,
    rgba(52, 211, 153, 0.12) 0%,
    transparent 70%
  );
  animation: pulse-ring 3s ease-in-out infinite;
}
@keyframes pulse-ring {
  0%,
  100% {
    transform: scale(1);
    opacity: 0.7;
  }
  50% {
    transform: scale(1.06);
    opacity: 1;
  }
}
.hero-avatar {
  width: 240px;
  height: 240px;
  border-radius: 50%;
  background: var(--surface);
  border: 2px solid rgba(52, 211, 153, 0.25);
  overflow: hidden;
  position: relative;
  z-index: 1;
  box-shadow: 0 0 60px rgba(52, 211, 153, 0.15);
}
.hero-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.availability-badge {
  position: absolute;
  bottom: -14px;
  left: 50%;
  transform: translateX(-50%);
  background: rgba(13, 21, 38, 0.95);
  border: 1px solid rgba(52, 211, 153, 0.3);
  border-radius: 30px;
  padding: 8px 18px;
  font-size: 12px;
  color: var(--green);
  white-space: nowrap;
  display: flex;
  align-items: center;
  gap: 8px;
  z-index: 2;
}
.pulse-dot {
  width: 8px;
  height: 8px;
  background: var(--green);
  border-radius: 50%;
  animation: pulse 2s infinite;
}
@keyframes pulse {
  0%,
  100% {
    box-shadow: 0 0 0 0 rgba(52, 211, 153, 0.5);
  }
  50% {
    box-shadow: 0 0 0 6px rgba(52, 211, 153, 0);
  }
}

/* ═══════════════════════════════════════════
   SECTIONS SHARED
═══════════════════════════════════════════ */
.section {
  padding: 100px 24px;
}
.dark-section {
  background: #080d1c;
}
.section-inner {
  max-width: 1200px;
  margin: 0 auto;
}
.section-label {
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: var(--green);
  margin-bottom: 12px;
}
.section-title {
  font-size: clamp(1.8rem, 4vw, 2.7rem);
  font-weight: 800;
  color: var(--text);
  margin: 0 0 16px;
}
.section-body {
  font-size: 1rem;
  color: var(--muted);
  line-height: 1.75;
  margin: 0 0 40px;
}

/* ═══════════════════════════════════════════
   ABOUT
═══════════════════════════════════════════ */
.about-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 40px;
}
@media (min-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr 1fr;
    align-items: start;
  }
}
.about-left .section-body {
  margin-bottom: 24px;
}
.about-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}
.about-tags span {
  background: rgba(52, 211, 153, 0.08);
  border: 1px solid rgba(52, 211, 153, 0.2);
  color: var(--green);
  padding: 7px 16px;
  border-radius: 20px;
  font-size: 13px;
  font-weight: 600;
}
.about-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 28px;
}
.about-card h3 {
  font-size: 17px;
  font-weight: 700;
  color: var(--text);
  margin: 0 0 20px;
}
.about-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.about-card li {
  display: flex;
  align-items: flex-start;
  gap: 14px;
}
.dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--green);
  flex-shrink: 0;
  margin-top: 5px;
}
.about-card li div {
  font-size: 14px;
  color: var(--muted);
  line-height: 1.5;
}
.about-card li div strong {
  color: var(--text);
}

/* ═══════════════════════════════════════════
   SKILLS
═══════════════════════════════════════════ */
.skills-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;
}
@media (min-width: 640px) {
  .skills-grid {
    grid-template-columns: 1fr 1fr;
  }
}
@media (min-width: 1024px) {
  .skills-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.skill-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 24px;
  transition:
    background var(--transition),
    border-color var(--transition),
    transform var(--transition);
}
.skill-card:hover {
  background: rgba(255, 255, 255, 0.06);
  border-color: rgba(52, 211, 153, 0.25);
  transform: translateY(-3px);
}
.skill-card-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 18px;
  color: var(--green);
}
.skill-card-header h3 {
  font-size: 15px;
  font-weight: 700;
  color: var(--text);
  margin: 0;
}
.skill-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.skill-pill {
  background: rgba(255, 255, 255, 0.07);
  border: 1px solid rgba(255, 255, 255, 0.09);
  color: var(--text);
  padding: 6px 14px;
  border-radius: 20px;
  font-size: 12.5px;
}

/* ═══════════════════════════════════════════
   PROJECTS
═══════════════════════════════════════════ */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}
@media (min-width: 640px) {
  .projects-grid {
    grid-template-columns: 1fr 1fr;
  }
}
@media (min-width: 1024px) {
  .projects-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.project-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 28px;
  display: flex;
  flex-direction: column;
  gap: 14px;
  transition:
    border-color var(--transition),
    transform var(--transition),
    box-shadow var(--transition);
  position: relative;
  overflow: hidden;
}
.project-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--green2), transparent);
  opacity: 0;
  transition: opacity 0.3s;
}
.project-card:hover {
  border-color: rgba(52, 211, 153, 0.3);
  transform: translateY(-4px);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
}
.project-card:hover::before {
  opacity: 1;
}

.project-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.project-icon-wrap {
  width: 52px;
  height: 52px;
  background: rgba(52, 211, 153, 0.1);
  border: 1px solid rgba(52, 211, 153, 0.2);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--green);
}
.project-status {
  display: flex;
  align-items: center;
  gap: 6px;
  font-size: 11px;
  font-weight: 600;
  color: var(--green);
  background: rgba(52, 211, 153, 0.1);
  border: 1px solid rgba(52, 211, 153, 0.2);
  padding: 5px 12px;
  border-radius: 20px;
}
.live-dot {
  width: 7px;
  height: 7px;
  background: var(--green);
  border-radius: 50%;
  animation: pulse 2s infinite;
}
.project-title {
  font-size: 20px;
  font-weight: 800;
  color: var(--text);
  margin: 0;
}
.project-url {
  font-size: 13px;
  color: var(--green2);
  font-family: monospace;
  margin: 0;
}
.project-desc {
  font-size: 14px;
  color: var(--muted);
  line-height: 1.65;
  margin: 0;
  flex: 1;
}
.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.project-tech span {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid var(--border);
  color: var(--muted);
  padding: 5px 12px;
  border-radius: 20px;
  font-size: 12px;
}
.project-link {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  color: var(--green);
  text-decoration: none;
  font-size: 13.5px;
  font-weight: 600;
  margin-top: 4px;
  transition: gap var(--transition);
}
.project-link:hover {
  gap: 10px;
}

/* ═══════════════════════════════════════════
   FOOTER / CONTACT
═══════════════════════════════════════════ */
.contact-footer {
  background: #080d1c;
  padding: 100px 24px 60px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.footer-glow {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 700px;
  height: 300px;
  background: radial-gradient(
    ellipse,
    rgba(52, 211, 153, 0.06) 0%,
    transparent 70%
  );
  pointer-events: none;
}
.footer-inner {
  max-width: 700px;
  margin: 0 auto;
  position: relative;
}
.footer-title {
  font-size: clamp(2rem, 5vw, 3.2rem);
  font-weight: 800;
  color: var(--text);
  margin: 12px 0 20px;
}
.footer-desc {
  font-size: 1rem;
  color: var(--muted);
  line-height: 1.75;
  margin-bottom: 48px;
}

.contact-links {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
  margin-bottom: 60px;
}
.contact-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 24px 36px;
  color: var(--text);
  text-decoration: none;
  min-width: 140px;
  cursor: pointer;
  transition:
    background var(--transition),
    border-color var(--transition),
    transform var(--transition);
  font: inherit;
}
.contact-card:hover {
  background: var(--surface-hover);
  border-color: rgba(255, 255, 255, 0.18);
  transform: translateY(-3px);
}
.contact-card.telegram:hover {
  border-color: rgba(36, 161, 222, 0.4);
  color: #24a1de;
}
.contact-card.resume-card:hover {
  border-color: rgba(52, 211, 153, 0.35);
  color: var(--green);
}
.contact-card span {
  font-size: 15px;
  font-weight: 700;
}
.contact-card small {
  font-size: 12px;
  color: var(--muted);
}

.footer-copy {
  font-size: 13px;
  color: rgba(148, 163, 184, 0.4);
  margin: 0;
}

/* ═══════════════════════════════════════════
   MODAL
═══════════════════════════════════════════ */
.modal-backdrop {
  position: fixed;
  inset: 0;
  z-index: 1000;
  background: rgba(0, 0, 0, 0.75);
  backdrop-filter: blur(8px);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 16px;
}
.modal-box {
  background: #0d1526;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  width: 100%;
  max-width: 900px;
  max-height: 92vh;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  box-shadow: 0 40px 120px rgba(0, 0, 0, 0.6);
}
.modal-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 18px 24px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  flex-shrink: 0;
}
.modal-title {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 15px;
  font-weight: 700;
  color: var(--text);
}
.modal-actions {
  display: flex;
  align-items: center;
  gap: 10px;
}
.btn-download {
  display: flex;
  align-items: center;
  gap: 6px;
  background: linear-gradient(135deg, var(--green2), #059669);
  color: #060a14;
  padding: 8px 18px;
  border-radius: 20px;
  font-size: 12.5px;
  font-weight: 700;
  text-decoration: none;
  transition: opacity var(--transition);
}
.btn-download:hover {
  opacity: 0.88;
}
.modal-close {
  background: rgba(255, 255, 255, 0.07);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 8px;
  color: var(--muted);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition:
    background var(--transition),
    color var(--transition);
}
.modal-close:hover {
  background: rgba(255, 255, 255, 0.12);
  color: var(--text);
}

.pdf-viewer-wrap {
  flex: 1;
  min-height: 0;
  position: relative;
  background: #1a1a2e;
}
.pdf-iframe {
  width: 100%;
  height: 100%;
  min-height: 500px;
  border: none;
  display: block;
}
.pdf-fallback {
  display: none;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 16px;
  padding: 60px 24px;
  color: var(--muted);
  font-size: 15px;
}
@media (max-width: 480px) {
  .pdf-iframe {
    display: none;
  }
  .pdf-fallback {
    display: flex;
  }
}

/* ═══════════════════════════════════════════
   MODAL TRANSITION
═══════════════════════════════════════════ */
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.25s ease;
}
.modal-enter-active .modal-box,
.modal-leave-active .modal-box {
  transition: transform 0.25s ease;
}
.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}
.modal-enter-from .modal-box,
.modal-leave-to .modal-box {
  transform: scale(0.95) translateY(20px);
}

@media (max-width: 480px) {
  .btn-resume:not(.mobile) {
    display: none;
  }
}
</style>
