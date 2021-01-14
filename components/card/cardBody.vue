<template>
  <div v-html="body" :class="{skeleton_text: body==='&nbsp;<br/><br/><br/><br/>'}">
  </div>
</template>

<script lang="ts">
export default {
  props: {
    body: String
  }
}
</script>

<style>
</style>
