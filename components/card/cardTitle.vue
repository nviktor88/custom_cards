<template>
  <h2 class="card-title" :class="{skeleton_text: title==='Loading'}">
    {{title}}
  </h2>
</template>

<script lang="ts">
export default {
  props: {
    title: String
  }
}
</script>

<style>
.card-title {
  margin-top: .5rem;
  margin-bottom: 0;
}
</style>
