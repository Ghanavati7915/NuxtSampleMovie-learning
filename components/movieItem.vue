<script setup lang="ts">
const props = defineProps({
  poster: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  genres: {
    type: Array,
    required: true,
  },
  year: {
    type: String,
    required: true,
  },
  country: {
    type: String,
    required: true,
  },
  imdb: {
    type: String,
    required: true,
  },
});
</script>

<template>

    <UCard>
      <template #header>
        <h3> {{props.title}} </h3>
      </template>

      <img :src="props.poster"/>
      <p>
        <span v-for="(item,i) in genres" :key="i"> [ {{item}} ] </span>
      </p>
      <p> {{props.year}} </p>
      <p> {{props.imdb}} </p>

      <template #footer>
        <p> {{props.country}} </p>
      </template>
    </UCard>
</template>

<style scoped>
.movie {
  width: 25%;
  border:solid 1px black;
  border-radius: 1.2rem;
  padding : 1.5rem;
  position : relative;
  display: inline-block;
  text-align: center;
  margin: 20px auto;
}
.movie>img {
  width: 100%;
  height: 200px;
  border-radius: 1.2rem;
  object-fit: contain;
}
</style>