<template>
  <header class="padding-1-5">
    <CardThumbnail v-if="thumbnail" :thumbnail="thumbnail"/>
    <div>
      <CardTitle v-if="title" :title="title"/>
      <CardSubtitle v-if="subtitle" :subtitle="subtitle"/>
    </div>
  </header>
</template>

<script lang="ts">
import CardThumbnail from './cardThumbnail.vue'
import CardTitle from './cardTitle.vue'
import CardSubtitle from './cardSubtitle.vue'

export default {
  components: {
    CardThumbnail,
    CardTitle,
    CardSubtitle
  },
  props: {
    thumbnail: String,
    title: String,
    subtitle: String,
  }
}
</script>

<style>
header {
  flex: 1 0 0%;
  flex-flow: row wrap;
  display: flex;
}
</style>
