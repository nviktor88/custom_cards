<template>
  <div class="thumbnail">
    <img :src="thumbnail" alt="Image">
  </div>
</template>

<script lang="ts">
export default {
  props: {
    thumbnail: String
  }
}
</script>

<style>
.thumbnail {
  padding-right: 1.5rem;
}

.thumbnail img {
  width: 3.75rem;
  height: 3.75rem;
}
</style>
