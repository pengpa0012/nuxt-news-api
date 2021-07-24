<template>
  <div class="flex justify-center mb-12 flex-col sm:flex-row text-center">
    <nuxt-link
      to="/"
      class="mb-4 sm:mb-0 mx-0 sm:mx-4 text-md sm:text-xl hover:bg-gray-900 hover:text-white py-2 px-6 rounded"
      >Trending News</nuxt-link
    >
    <nuxt-link
      to="/search"
      class="mx-0 sm:mx-4 text-md sm:text-xl hover:bg-gray-900 hover:text-white py-2 px-6 rounded"
      >Search News</nuxt-link
    >
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
a.nuxt-link-exact-active {
  color: #fff;
  background: #000;
}
</style>
