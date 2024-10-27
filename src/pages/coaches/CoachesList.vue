<template>
  <BaseCard>
    <section>FILTER</section>
    <section>
      <div class="controls">
        <BaseButton mode="outline" @click="refreshCoaches">Refresh</BaseButton>
        <BaseButton link :to="'/register'">Register as Coach</BaseButton>
      </div>
      <ul v-if="hasCoaches">
        <CoachItem
          v-for="coach in filteredCoaches"
          :key="coach.id"
          :id="coach.id"
          :firstName="coach.firstName"
          :lastName="coach.lastName"
          :rate="coach.hourlyRate"
          :areas="coach.areas"
        />
      </ul>
      <h3 v-else>No coaches found.</h3>
    </section>
  </BaseCard>
</template>

<script>
import CoachItem from '@/components/coaches/CoachItem.vue';
import BaseButton from '@/components/ui/BaseButton.vue';
import BaseCard from '@/components/ui/BaseCard.vue';

export default {
  components: { CoachItem, BaseButton, BaseCard },
  computed: {
    filteredCoaches() {
      return this.$store.getters['coaches/coaches'];
    },
    hasCoaches() {
      return this.$store.getters['coaches/hasCoaches'];
    },
  },
  methods: {
    refreshCoaches() {
      console.log('Refresh coaches list');
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
.controls {
  display: flex;
  justify-content: space-between;
}
</style>
