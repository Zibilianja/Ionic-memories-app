<template>
  <base-layout page-title="All Memories">  
  <template v-slot:actions-end>
      <ion-button router-link="/memories/add">
          <ion-icon slot="icon-only" :icon="add"></ion-icon>
      </ion-button>
  </template>
    <memory-list :memories="memories"></memory-list>
    </base-layout>
</template>

<script>
import { IonIcon, IonButton } from "@ionic/vue"
import { add } from 'ionicons/icons'
import MemoryList from "../components/memories/MemoriesList.vue"

export default {
  components: {
    MemoryList,
    IonIcon, 
    IonButton
  },
  data() {
      return { add }
  },
  computed: {
      memories() {
          return this.$store.getters.memories
      }
  }
};
</script>
