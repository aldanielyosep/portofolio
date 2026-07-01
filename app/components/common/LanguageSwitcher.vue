<template>
  <NuxtLink
    :to="targetLocalePath"
    class="inline-flex items-center gap-2 rounded-full border border-brand-300/70 bg-brand-50 px-3 py-2 text-sm font-semibold text-brand-700 backdrop-blur-sm transition hover:bg-brand-100 dark:border-brand-500/50 dark:bg-brand-950/40 dark:text-brand-200 dark:hover:bg-brand-950/60"
  >
    <Icon name="i-lucide-languages" class="size-4" />
    <span>{{ t('layout.switchLanguage') }}</span>
    {{ localeLabel }}
  </NuxtLink>
</template>

<script setup lang="ts">
const { locale, t } = useI18n()
const switchLocalePath = useSwitchLocalePath()

const localeLabel = computed(() =>
  locale.value === 'en' ? t('layout.languageShort.id') : t('layout.languageShort.en'),
)

const targetLocalePath = computed(() => switchLocalePath(locale.value === 'en' ? 'id' : 'en'))
</script>
