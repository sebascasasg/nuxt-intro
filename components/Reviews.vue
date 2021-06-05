<template>
  <div>
    <h3>customer Reviews</h3>
    <div v-if="!$fetchState.pending">
      <ReviewCard
        v-for="reviewer in reviewers.results"
        :key="reviewer.login.uuid"
        :review="reviewer"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      reviewers: []
    };
  },
  async fetch() {
    this.reviewers = await fetch(
      "https://randomuser.me/api/?results=5"
    ).then(res => res.json());
  }
};
</script>

<style scoped></style>
