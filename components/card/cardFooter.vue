<template>
  <footer class="card-footer padding-1-5" v-html="footer" :class="{skeleton_text: footer==='&nbsp;'}"/>
</template>

<script lang="ts">
export default {
  props: {
    footer: String
  }
}
</script>

<style>
.card-footer {
  border-top: 1px solid rgba(0,0,0,.125);
  border-radius: 0 0 calc(.5rem - 1px) calc(.5rem - 1px);
}
</style>
