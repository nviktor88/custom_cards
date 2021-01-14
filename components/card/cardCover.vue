<template>
  <img :src="cover" alt="Image" class="cover-image"
       :class="[{top: cover_place==='above'},{cover_height_12_5: cover_height==='12.5rem'}]"
  >
</template>

<script lang="ts">
export default {
  props: {
    cover: String,
    cover_place: String,
    cover_height: String
  }
}
</script>

<style>
.cover-image {
  object-fit: cover;
  max-width: 100%;
}

.cover_height_12_5 {
  max-height: 12.5rem;
  width: 100%;
}

.top {
  border-top-left-radius: calc(.5rem - 1px);
  border-top-right-radius: calc(.5rem - 1px);
}
</style>
