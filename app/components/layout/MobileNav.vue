<template>
  <Transition
    enter-active-class="duration-200 ease-out"
    enter-from-class="opacity-0"
    enter-to-class="opacity-100"
    leave-active-class="duration-150 ease-in"
    leave-from-class="opacity-100"
    leave-to-class="opacity-0"
  >
    <div v-if="open" class="fixed inset-0 z-50 md:hidden">
      <button
        type="button"
        class="absolute inset-0 bg-slate-950/50"
        :aria-label="t('layout.closeMenu')"
        @click="$emit('close')"
      />

      <Transition
        enter-active-class="duration-200 ease-out"
        enter-from-class="translate-x-full"
        enter-to-class="translate-x-0"
        leave-active-class="duration-150 ease-in"
        leave-from-class="translate-x-0"
        leave-to-class="translate-x-full"
      >
        <aside
          v-if="open"
          class="absolute right-0 top-0 flex h-full w-80 max-w-[85vw] flex-col border-l border-slate-200 bg-white px-5 py-6 dark:border-slate-800 dark:bg-slate-950"
        >
          <div class="mb-6 flex items-center justify-between">
            <p class="font-semibold">{{ t('layout.menu') }}</p>
            <button
              type="button"
              class="rounded-lg border border-slate-300 p-2 dark:border-slate-700"
              :aria-label="t('layout.closeMenu')"
              @click="$emit('close')"
            >
              <Icon name="i-lucide-x" class="size-4" />
            </button>
          </div>

          <nav class="flex flex-col gap-2">
            <a
              v-for="item in links"
              :key="item.href"
              :href="item.href"
              class="rounded-lg px-3 py-2 text-sm font-medium text-slate-700 transition hover:bg-slate-100 dark:text-slate-200 dark:hover:bg-slate-900"
              @click="$emit('close')"
            >
              {{ item.label }}
            </a>
          </nav>

          <div class="mt-auto flex flex-wrap gap-2 pt-6">
            <LanguageSwitcher />
            <ThemeSwitcher />
          </div>
        </aside>
      </Transition>
    </div>
  </Transition>
</template>

<script setup lang="ts">
defineProps<{
  open: boolean
}>()

defineEmits<{
  close: []
}>()

const { t } = useI18n()

const links = computed(() => [
  { label: t('layout.nav.home'), href: '#home' },
  { label: t('layout.nav.about'), href: '#about' },
  { label: t('layout.nav.projects'), href: '#projects' },
  { label: t('layout.nav.contact'), href: '#contact' },
])
</script>
