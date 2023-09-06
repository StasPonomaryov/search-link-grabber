<script>
import { ref, computed } from 'vue';

export default {
  setup() {
    const searchQuery = ref('');
    const searchResults = ref('');

    const search = async () => {
      if (searchQuery.value) {
        try {
          const response = await fetch(
            `https://www.googleapis.com/customsearch/v1?key=${import.meta.env.VITE_GOOGLE_TOKEN}&cx=${import.meta.env.VITE_GOOGLE_CX}&q=${searchQuery.value}`
          );
          const data = await response.json();
          searchResults.value = data.items.map(item => item.link).join('\n');
        } catch (error) {
          console.error('Помилка при отриманні результатів пошуку', error);
        }
      }
    };
    const filteredSearchResults = computed(() => {
      if (!searchResults.value) return '';
      const resultsArray = searchResults.value.split('\n');
      const regex = /(?:http(?:s)?:\/\/)?(?:www\.)?(?:play\.google\.com\/|itunes\.apple\.com\/)(?:.+\/)?/g;
      const filteredResults = resultsArray.filter(result => !result.match(regex));
      return filteredResults.join('\n');
    });

    return {
      searchQuery,
      searchResults,
      search,
      filteredSearchResults,
    };
  },
}
</script>

<template>
  <div class="search-wrapper">
    <form @submit.prevent>
      <input-text v-model="searchQuery" />
      <button-simple @click="search">Search</button-simple>
    </form>
  </div>
  <div class="results-wrapper">
    <textarea-simple :disabled="true" :text="filteredSearchResults"></textarea-simple>
  </div>
</template>
