<template>
  <button
    type="button"
    class="inline-flex items-center gap-2 rounded-lg border border-slate-300/80 bg-white/80 px-3 py-2 text-sm font-medium text-slate-700 backdrop-blur-sm transition hover:border-brand-300 hover:text-brand-700 dark:border-slate-700 dark:bg-slate-900/60 dark:text-slate-200 dark:hover:border-brand-500 dark:hover:text-brand-300"
    @click="toggleLocale"
  >
    <Icon name="i-lucide-languages" class="size-4" />
    {{ localeLabel }}
  </button>
</template>

<script setup lang="ts">
const { locale, t } = useI18n()

const localeLabel = computed(() =>
  locale.value === 'en' ? t('layout.languageShort.id') : t('layout.languageShort.en'),
)

const toggleLocale = () => {
  locale.value = locale.value === 'en' ? 'id' : 'en'
}
</script>
