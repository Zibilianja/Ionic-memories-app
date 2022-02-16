<template>
  <base-layout page-title="Add a Memory" page-default-back-link="/memories">
    <add-memory-form @save-memory="saveMemory"></add-memory-form>
  </base-layout>
</template>

<script>
import BaseLayout from "../components/base/BaseLayout.vue";
import AddMemoryForm from "../components/memories/AddMemoryForm.vue"
export default {
  components: {
    BaseLayout,
    AddMemoryForm
  },
  methods: {
      saveMemory(memoryData) {
          this.$store.dispatch('addMemory', memoryData);
          this.$router.replace('/memories')
      }
  }
};
</script>
