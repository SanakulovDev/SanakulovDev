<template>
  <div class="min-h-screen bg-slate-950 text-slate-100 scroll-smooth">
    <header class="sticky top-0 z-20 border-b border-white/10 bg-slate-950/80 backdrop-blur">
      <div class="mx-auto flex max-w-6xl items-center justify-between px-4 py-4">
        <div class="flex items-center gap-3">
          <span class="inline-flex h-9 w-9 items-center justify-center rounded-full bg-white/10 text-sm font-semibold">
            S
          </span>
          <div>
            <p class="text-sm uppercase tracking-[0.2em] text-slate-400">sanakulov.uz</p>
            <p class="text-base font-semibold">Sanakulov</p>
          </div>
        </div>
        <nav class="hidden gap-6 text-sm text-slate-300 md:flex">
          <a class="hover:text-white" href="#hero">Home</a>
          <a class="hover:text-white" href="#about">About</a>
          <a class="hover:text-white" href="#skills">Skills</a>
          <a class="hover:text-white" href="#contact">Contact</a>
        </nav>
        <a
          class="rounded-full border border-white/20 px-4 py-2 text-xs font-semibold uppercase tracking-widest text-white transition hover:border-white/50"
          href="#contact"
        >
          Hire Me
        </a>
      </div>
    </header>

    <main class="mx-auto flex max-w-6xl flex-col gap-24 px-4 pb-20 pt-16">
      <section id="hero" class="grid items-center gap-10 md:grid-cols-[1.1fr_0.9fr]">
        <div class="space-y-6">
          <p class="text-sm uppercase tracking-[0.25em] text-emerald-400">Backend Developer</p>
          <h1 class="text-4xl font-semibold leading-tight text-white sm:text-5xl">
            Salom, I'm Sanakulov.
            <span class="block text-slate-400">I build reliable backend systems.</span>
          </h1>
          <p class="text-base text-slate-300 sm:text-lg">
            25-year-old backend developer currently at BTS EXPRESS. I focus on clean APIs, scalable
            infrastructure, and fast delivery.
          </p>
          <div class="flex flex-wrap gap-4">
            <a
              class="rounded-full bg-emerald-400 px-6 py-3 text-xs font-semibold uppercase tracking-widest text-slate-950 transition hover:bg-emerald-300"
              href="#skills"
            >
              View Skills
            </a>
            <a
              class="rounded-full border border-white/20 px-6 py-3 text-xs font-semibold uppercase tracking-widest text-white transition hover:border-white/50"
              href="#about"
            >
              About Me
            </a>
          </div>
        </div>
        <div class="flex justify-center md:justify-end">
          <div class="relative h-52 w-52 rounded-full border border-white/10 bg-white/5 p-2 sm:h-64 sm:w-64">
            <img
              alt="Sanakulov portrait placeholder"
              class="h-full w-full rounded-full object-cover"
              :src="profileImage"
            />
            <div class="absolute -bottom-4 left-1/2 w-36 -translate-x-1/2 rounded-full bg-white/10 px-3 py-2 text-center text-xs text-slate-200">
              Open to new projects
            </div>
          </div>
        </div>
      </section>

      <section id="about" class="grid gap-10 md:grid-cols-[0.8fr_1.2fr]">
        <div class="space-y-4">
          <p class="text-sm uppercase tracking-[0.25em] text-emerald-400">About</p>
          <h2 class="text-3xl font-semibold text-white">Building with purpose.</h2>
          <p class="text-base text-slate-300">
            I am 25, based in Uzbekistan, and currently crafting backend solutions at BTS EXPRESS.
            My education spans Tashkent University of Information Technologies (TUIT) and the System
            Design program at 42.uz.
          </p>
        </div>
        <div class="space-y-4 rounded-3xl border border-white/10 bg-white/5 p-6">
          <h3 class="text-lg font-semibold text-white">Highlights</h3>
          <ul class="space-y-3 text-sm text-slate-300">
            <li class="flex items-center gap-3">
              <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
              Backend Developer at BTS EXPRESS
            </li>
            <li class="flex items-center gap-3">
              <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
              Graduate of TUIT, specializing in information technologies
            </li>
            <li class="flex items-center gap-3">
              <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
              Completed System Design course at 42.uz
            </li>
          </ul>
        </div>
      </section>

      <section id="skills" class="space-y-10">
        <div class="space-y-3">
          <p class="text-sm uppercase tracking-[0.25em] text-emerald-400">Skills</p>
          <h2 class="text-3xl font-semibold text-white">Tech stack</h2>
          <p class="text-base text-slate-300">
            Expert in backend foundations with a focus on performance and reliability.
          </p>
        </div>
        <div class="grid gap-6 md:grid-cols-2">
          <div class="rounded-3xl border border-white/10 bg-white/5 p-6">
            <h3 class="text-lg font-semibold text-white">Expert</h3>
            <ul class="mt-4 flex flex-wrap gap-2 text-sm text-slate-200">
              <li v-for="item in expertSkills" :key="item" class="rounded-full bg-white/10 px-4 py-2">
                {{ item }}
              </li>
            </ul>
          </div>
          <div class="rounded-3xl border border-white/10 bg-white/5 p-6">
            <h3 class="text-lg font-semibold text-white">Familiar</h3>
            <ul class="mt-4 flex flex-wrap gap-2 text-sm text-slate-200">
              <li v-for="item in familiarSkills" :key="item" class="rounded-full bg-white/10 px-4 py-2">
                {{ item }}
              </li>
            </ul>
          </div>
        </div>
      </section>
    </main>

    <footer id="contact" class="py-20 px-4 text-center">
      <h2 class="text-3xl font-bold text-white mb-8">Get In Touch</h2>
      <p class="text-slate-400 mb-8 max-w-xl mx-auto">
        Loyihalar yoki hamkorlik bo'yicha gaplashmoqchimisiz? Menga Telegram orqali yozing yoki kodlarimni GitHubda ko'ring.
      </p>

      <div class="flex justify-center gap-6">
        
        <a href="https://github.com/SanakulovDev" target="_blank" class="text-slate-400 hover:text-white transition-colors transform hover:scale-110">
          <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
            <path fill-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" clip-rule="evenodd" />
          </svg>
        </a>

        <a href="https://t.me/Sanakulov_dev" target="_blank" class="text-slate-400 hover:text-[#24A1DE] transition-colors transform hover:scale-110">
          <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
            <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.638z"/>
          </svg>
        </a>

      </div>
      
      <p class="text-xs text-slate-600 mt-12">
        © 2026 Sanakulov. Backend Developer.
      </p>
    </footer>
  </div>
</template>

<script setup>
import profileImage from "./profile.jpg";

const expertSkills = ["PHP (Yii2)", "HTML", "CSS", "PostgreSQL", "MySQL"];
const familiarSkills = ["Python", "Go (Golang)"];
</script>
