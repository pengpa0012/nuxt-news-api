<template>
  <div class="max-w-4xl mx-auto px-6">
    <div class="py-12 text-center font-light">
      <span class="text-sm sm:text-lg text-gray-500 mb-4 block"
        >Made by Godfrey Necesario</span
      >
      <h1 class="text-3xl sm:text-6xl">
        Nuxt News <span class="font-bold">API</span>
      </h1>
    </div>
    <Navbar />
    <Nuxt />
  </div>
</template>

<script>
export default {};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noticia+Text:ital,wght@0,400;0,700;1,400&display=swap");

html {
  --lh: 1.4rem;
  line-height: var(--lh);
}

body {
  font-family: "Noticia Text", serif;
}

img {
  max-height: 400px;
  object-fit: cover;
}

.truncate-overflow {
  --max-lines: 6;
  position: relative;
  max-height: calc(var(--lh) * var(--max-lines));
  overflow: hidden;
  padding-right: 1rem; /* space for ellipsis */
}
.truncate-overflow::before {
  position: absolute;
  content: "...";
  inset-block-end: 0; /* "bottom" */
  inset-inline-end: 0; /* "right" */
}
.truncate-overflow::after {
  content: "";
  position: absolute;
  inset-inline-end: 0; /* "right" */
  width: 1rem;
  height: 1rem;
  background: white;
}
</style>
