<template>
  <div class="container">
    <div class="card-deck" :class="{not_equal: !grid}">
      <Skeleton v-if="!cards.length" class="skeleton">
        <Card cover="image_skeleton.png"
              cover_place="above"
              cover_height="12.5rem"
              thumbnail="thumbnail_skeleton.png"
              title="Loading"
              subtitle="cards..."
              body="&nbsp;<br/><br/><br/><br/>"
              footer="&nbsp;"
              :skeleton=true>
        </Card>
      </Skeleton>
      <Card v-for="card in cards"
            :key="card.id"
            :id="card.id"
            :cover="card.cover"
            :cover_place="card.cover_place"
            :cover_height="card.cover_height"
            :thumbnail="card.thumbnail"
            :title="card.title"
            :subtitle="card.subtitle"
            :body="card.body"
            :footer="card.footer"
            :active="card.id===selectedCardId"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { Skeleton } from 'vue-loading-skeleton';
import Card from '~/components/card/card.vue'
import json from '~/sample/cards.json'

export default {
  components: {
    Card,
    Skeleton
  },
  data() {
    return {
      grid: true,
      cards: [],
      selectedCardId: 0
    }
  },
  mounted() {
    (this as any).loadCards();
  },
  methods: {
    loadCards() {
      setTimeout(() => {
        console.log('Cards have loaded...');
        (this as any).cards = json.cards;
      }, 3000);
    },
    setCardActive(cardId: string) {
      (this as any).selectedCardId = cardId;
      alert("Selected card is " + cardId + ".");
    },
  }
}
</script>

<style>

html {
  font-family: "Helvetica Neue",serif;
}

.card-deck {
  display: flex;
  flex-flow: row wrap;
  color: #2d2d2d;
  margin-left: 0;
  margin-right: 0;
}

.not_equal {
  align-items: flex-start;
}

@media (min-width: 576px) {
  .card-deck .card {
    flex: 1 0 calc(100%/3);
    margin-left: 0.875rem;
    margin-right: 0.875rem;
  }
}


@media (min-width: 818px) {
  .card-deck .card {
    flex: 1 0 calc(100%/4);
  }
}

@media (min-width: 1060px) {
  .card-deck .card {
    flex: 1 0 calc(100%/5);
  }
}

@media (min-width: 1302px) {
  .card-deck .card {
    flex: 1 0 calc(100%/6);
  }
}

@media (min-width: 1544px) {
  .card-deck .card {
    flex: 1 0 calc(100%/6);
  }
}

.skeleton {
  width:100%;
  max-width: 20rem;
}
</style>
