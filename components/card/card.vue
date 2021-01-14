<template>
  <div class="card" @click="makeActive" :class="{active: active, skeleton: skeleton}">
    <CardCover
      v-if="cover_place==='above' && cover"
      :cover="cover"
      :cover_place="cover_place"
      :cover_height="cover_height"/>
    <div class="card-body">
      <CardHeader
        v-if="thumbnail || title || subtitle"
        :thumbnail="thumbnail"
        :title="title"
        :subtitle="subtitle"/>
      <CardCover
        v-if="cover_place==='under' && cover"
        :cover="cover"
        :cover_place="cover_place"
        :cover_height="cover_height"/>
      <CardBody class="padding-1-5" v-if="body" :body="body"/>
    </div>
    <CardFooter v-if="footer" :footer="footer"/>
  </div>
</template>

<script lang="ts">
import CardCover from './cardCover.vue';
import CardHeader from './cardHeader.vue';
import CardBody from './cardBody.vue';
import CardFooter from './cardFooter.vue';
export default {
  components: {
    CardCover,
    CardHeader,
    CardBody,
    CardFooter
  },
  props: {
    id: Number,
    cover: String,
    cover_place: String,
    cover_height: String,
    thumbnail: String,
    title: String,
    subtitle: String,
    body: String,
    footer: String,
    active: Boolean,
    skeleton: Boolean
  },
  methods: {
    makeActive() {
      (this as any).$parent.setCardActive((this as any).id);
    }
  }
}
</script>

<style>
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: #fff;
  background-clip: border-box;
  border: 1px solid rgba(0,0,0,.125);
  border-radius: .5rem;
  flex: 1 1 auto;
  min-height: 0.063rem;
  //max-width: 25rem;
  margin-bottom: 1rem;
}

.card:hover {
  background-color: #f7f7f7;
}

.card.active {
  border: 1px solid #31268a;
  box-shadow: 0 0 0pt 2pt #d5d4e7;
}

.card.skeleton {
  background-color: #fafafa;
}

.card-body {
  flex: 1 1 auto;
  min-height: 0.063rem;
}

.padding-1-5 {
  padding: 1.5rem;
}

.skeleton_text {
  background-clip: content-box;
  background-color: #F0F0F0;
}
</style>
