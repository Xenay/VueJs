<template>
 <div class="row">
 <div class="col-2"></div>
 <div class="col-7">
  <instagram-card v-for="card in cards" :key="card" :info="card" />

 </div>
 <div class="col-3">
 ... ovdje ide desni stupac!
 </div>
 </div>
</template>

<script>
// @ is an alias to /src
import InstagramCard from '@/components/InstagramCard.vue'

let cards = [];

cards = [
  "https://picsum.photos/id/1/400/400",
  "https://picsum.photos/id/3/400/400",
  "https://picsum.photos/id/5/400/400",
]


export default {
  props: ["info"],
  name: 'home',
  data: function() {
    return {
        cards: cards,
    }
  },
  components: {
    InstagramCard
  }
}
</script>

<style scoped>

</style>
