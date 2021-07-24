<template>
  <div>
    <div
      v-for="news in AllNews"
      :key="news.id"
      class="mb-12 shadow-lg rounded-lg overflow-hidden"
    >
      <img
        :src="news.image.url || 'https://via.placeholder.com/1920x1280'"
        onerror="javascript: this.src = 'https://via.placeholder.com/1920x1280'"
        alt="poster image"
        class="w-full"
      />
      <div
        class="p-5 pb-12 border border-gray-200 border-l-0 border-r-0 border-b-0"
      >
        <div class="flex mb-4 y">
          <div>
            <h1 class="font-black text-xl">
              {{ news.title }}
            </h1>
            <p class="text-gray-600 italic">Source: {{ news.provider.name }}</p>
          </div>
        </div>
        <p class="truncate-overflow text-justify mb-8 text-gray-900">
          {{ news.body }}
        </p>
        <a
          :href="news.url"
          target="_blank"
          class="text-lg py-2 px-6 bg-gray-800 hover:bg-gray-900 text-white rounded"
        >
          Read More
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    AllNews: {
      type: Array,
      default: []
    }
  }
};
</script>

<style></style>
