<template>
 <div class="row">
 <div class="col-2"></div>
 <div class="col-7">
  <instagram-card v-for="card in filteredCards" :key="card.url" :info="card" />

 </div>
 <div class="col-3">
 <input v-model='ime' placeholder="Upišite ime">
 <input v-model='prezime' placeholder="Upišite prezime">
 
 <p>{{ime}} {{prezime}}</p>
 </div>
 </div>
</template>

<script>
// @ is an alias to /src
import InstagramCard from '@/components/InstagramCard.vue'
import store from "@/store";

let cards = [];
let ime= [];
let prezime = [];


cards = [
  {url  : 'https://picsum.photos/id/1/400/400',
  "description": "laptop",
  time: 'few minutes ago...'},
  {url  : 'https://picsum.photos/id/5/400/400',
  "description": "laptop",
  time: 'few minutes ago...'},
  {url  : 'https://picsum.photos/id/10/400/400',
  "description": "laptop",
  time: 'few minutes ago...'},
]


export default {
  props: ["info"],
  name: 'home',
  data: function() {
    return {
        cards,
        store,
        ime: "",
        prezime: "",
        imePrint:"",
        prezimePrint:"",
      
       
    }
  },
  computed: {
    
     filteredCards() {
       let termin = this.store.searchTerm;

       return this.cards.filter(card => card.description.includes(termin));
       

    
     },
    
    
  },

  
  imePrezime() {
      this.imePrint=this.ime;
      this.prezimePrint=this.prezime;
    },

  
  components: {
    InstagramCard,
  }
}
</script>

<style scoped>

</style>
