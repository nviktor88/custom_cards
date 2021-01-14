<template>
  <div class="subtitle" :class="{skeleton_text: subtitle==='cards...'}">
    {{subtitle}}
  </div>
</template>

<script lang="ts">
export default {
  props: {
    subtitle: String
  }
}
</script>

<style>
.subtitle {
  color: #6e6e6e;
}
</style>
