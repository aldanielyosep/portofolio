<template>
  <header
    class="sticky top-0 z-40 border-b border-slate-200/80 bg-white/85 backdrop-blur-md dark:border-slate-800 dark:bg-slate-950/80"
  >
    <div class="mx-auto flex w-full max-w-6xl items-center justify-between px-4 py-3 sm:px-6">
      <a href="#home" class="inline-flex items-center gap-2 text-sm font-semibold tracking-wide">
        <span
          class="inline-flex size-7 items-center justify-center rounded-md bg-brand-500 text-white"
          >D</span
        >
        <span>Daniel Yosep</span>
      </a>

      <nav class="hidden items-center gap-1 md:flex">
        <a
          v-for="item in links"
          :key="item.href"
          :href="item.href"
          class="rounded-md px-3 py-2 text-sm text-slate-700 transition hover:bg-slate-100 hover:text-slate-900 dark:text-slate-200 dark:hover:bg-slate-900"
        >
          {{ item.label }}
        </a>
      </nav>

      <div class="hidden items-center gap-2 md:flex">
        <LanguageSwitcher />
        <ThemeSwitcher />
      </div>

      <button
        type="button"
        class="inline-flex items-center gap-2 rounded-lg border border-slate-300 px-3 py-2 text-sm font-medium md:hidden dark:border-slate-700"
        :aria-label="t('layout.openMenu')"
        @click="isOpen = true"
      >
        <Icon name="i-lucide-menu" class="size-4" />
        {{ t('layout.menu') }}
      </button>
    </div>

    <MobileNav :open="isOpen" @close="isOpen = false" />
  </header>
</template>

<script setup lang="ts">
const { t } = useI18n()
const isOpen = ref(false)

const links = computed(() => [
  { label: t('layout.nav.home'), href: '#home' },
  { label: t('layout.nav.about'), href: '#about' },
  { label: t('layout.nav.projects'), href: '#projects' },
  { label: t('layout.nav.contact'), href: '#contact' },
])
</script>
