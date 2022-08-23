<script setup>
const { data: surahs } = await useFetch(
  "https://quran-api-clone.vercel.app/surah"
);
</script>

<template>
  <header class="flex justify-between items-center mb-5">
    <h1 class="text-xl font-bold text-emerald-800 dark:text-emerald-600">
      Quran Web
    </h1>
    <div class="flex items-center space-x-4">
      <NuxtLink to="/bookmark">
        <IconBookmark class="text-emerald-800 dark:text-emerald-600 h-7 w-7" />
      </NuxtLink>
      <button>
        <IconMoon class="text-emerald-800 dark:text-emerald-600 h-7 w-7" />
      </button>
    </div>
  </header>

  <main>
    <div
      class="bg-gradient-to-br from-green-800 to-emerald-600 text-white p-4 w-full mb-6 rounded-lg shadow-lg shadow-emerald-200/50 dark:shadow-none"
    >
      <p class="font-medium mb-16 flex items-center space-x-2">
        <IconBook class="text-white h-7 w-7" />
        <span> Terakhir Dibaca </span>
      </p>
    </div>
    <SurahSearch />
    <div class="flex flex-col gap-5">
      <SurahList
        v-for="surah in surahs.data"
        :key="surah.number"
        :surah="surah"
      />
    </div>
  </main>
</template>
