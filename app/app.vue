<template>
  <div
    class="min-h-screen bg-gradient-to-b from-brand-50/60 via-white to-white dark:from-slate-900 dark:via-slate-950 dark:to-slate-950"
  >
    <NuxtRouteAnnouncer />
    <AppNavbar />

    <main class="mx-auto w-full max-w-6xl px-4 pb-24 pt-12 sm:px-6">
      <section id="home" class="scroll-mt-28 py-14">
        <p
          class="mb-4 inline-flex items-center gap-2 rounded-full border border-brand-200 bg-brand-50 px-3 py-1 text-sm text-brand-700 dark:border-brand-900/60 dark:bg-brand-900/30 dark:text-brand-200"
        >
          <Icon name="i-lucide-layout-template" class="size-4" />
          {{ t('layout.phaseReady') }}
        </p>
        <h1 class="max-w-3xl text-4xl font-bold tracking-tight sm:text-5xl">
          {{ t('common.title') }}
        </h1>
        <p class="mt-4 max-w-2xl text-base text-slate-600 dark:text-slate-300">
          {{ t('common.description') }}
        </p>
      </section>

      <section id="about" class="scroll-mt-28 py-14">
        <h2 class="text-2xl font-semibold">{{ t('layout.nav.about') }}</h2>
        <p class="mt-3 max-w-2xl text-slate-600 dark:text-slate-300">
          {{ t('layout.placeholder.about') }}
        </p>
      </section>

      <section id="projects" class="scroll-mt-28 py-14">
        <h2 class="text-2xl font-semibold">{{ t('layout.nav.projects') }}</h2>
        <p class="mt-3 max-w-2xl text-slate-600 dark:text-slate-300">
          {{ t('layout.placeholder.projects') }}
        </p>
      </section>

      <section id="contact" class="scroll-mt-28 py-14">
        <h2 class="text-2xl font-semibold">{{ t('layout.nav.contact') }}</h2>
        <p class="mt-3 max-w-2xl text-slate-600 dark:text-slate-300">
          {{ t('layout.placeholder.contact') }}
        </p>
      </section>
    </main>

    <AppFooter />
    <ScrollToTopButton />
  </div>
</template>

<script setup lang="ts">
const { t } = useI18n()
</script>
