<template>
  <NuxtLink :to="`/products/${cardInfo.id}`" class="card">
    <img
      :src="require(`@/assets/images/${cardInfo.image || 'fe1.jpg'}`)"
      alt=""
      class="image"
    />
    <h3 class="header">{{ cardInfo.title }}</h3>
    <p class="snippet">{{ cardInfo.snippet }}</p>
  </NuxtLink>
</template>

<script>
export default {
  props: {
    cardInfo: {
      type: Object
    }
  }
};
</script>

<style scoped>
.card {
  width: 31.5%;
  height: 25rem;
  border: none;
  overflow: hidden;
  padding: 0;
  cursor: pointer;
}
.image {
  height: 65%;
  border-radius: 0.5rem;
}
.header {
  font-size: 1.15rem;
  margin-top: 0.4rem;
}
.snippet {
  color: grey;
}
</style>
