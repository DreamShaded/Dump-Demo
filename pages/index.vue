<template>
  <div class="page">
    <div class="grid-container">
      <div class="grid-item chapter" />
      <div class="grid-item article" />
    </div>
  </div>
</template>

<script lang="ts" setup>
useHead({
  title: 'Hello, world!',
});
</script>

<style lang="css">
.grid-container {
  display: grid;
  grid-template:
    "chapter article1 article2"
    "chapter article3 article4"
}

.grid-container {
  /* автоматом применяется, если есть
  container-type или name */
  contain: layout;
  container-type: inline-size;
}

.chapter {
  grid-area: chapter;
}

.article:nth-child(2) { grid-area: article1; }
.article:nth-child(3) { grid-area: article2; }
.article:nth-child(4) { grid-area: article3; }
.article:nth-child(5) { grid-area: article4; }

@media (width <= 768px) {
  .grid-container {
    grid-template-areas:
      "chapter"
      "article1"
      "article2"
      "article3"
      "article4";
    grid-template-columns: 1fr;
    grid-template-rows: auto;
  }
}

@container (max-width: 768px) {
  .grid-container {
    grid-template-areas:
      "chapter"
      "article1"
      "article2"
      "article3"
      "article4";
    grid-template-columns: 1fr;
    grid-template-rows: auto;
  }
}

</style>
