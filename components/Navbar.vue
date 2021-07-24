<template>
  <div class="flex justify-center mb-12">
    <nuxt-link
      to="/"
      class="mx-4 text-xl hover:bg-gray-900 hover:text-white py-2 px-6 rounded"
      >Trending News</nuxt-link
    >
    <nuxt-link
      to="/search"
      class="mx-4 text-xl hover:bg-gray-900 hover:text-white py-2 px-6 rounded"
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
