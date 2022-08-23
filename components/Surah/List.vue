<script setup>
const props = defineProps({
  surah: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <NuxtLink
    :to="{ name: 'surah-id', params: { id: props.surah.number } }"
    class="box-border w-full bg-white p-4 flex gap-3 items-center shadow-md rounded-lg shadow-gray-200/50"
  >
    <IconNumberContainer>
      {{ props.surah.number }}
    </IconNumberContainer>
    <div>
      <h3 class="font-semibold text-emerald-800 mb-0.5">
        {{ props.surah.name.transliteration.id }}
      </h3>
      <p class="text-gray-400 text-sm">
        {{ surah.revelation.id }},
        <span>{{ surah.numberOfVerses }} ayat</span>
      </p>
    </div>
    <div class="ml-auto">
      <p class="font-serif text-2xl text-emerald-600">
        {{ surah.name.short }}
      </p>
    </div>
  </NuxtLink>
</template>
