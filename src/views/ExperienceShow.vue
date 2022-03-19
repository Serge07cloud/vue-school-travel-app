<template>
  <section>
    <h1>{{ experience.name }}</h1>
    <img :src="`/images/${experience?.image}`" :alt="experience?.name" />
    <p>{{ experience.description }}</p>
  </section>
</template>

<script setup lang="ts">
import { computed, toRef } from "@vue/runtime-core";
import sourceData from "../data.json";

const props = defineProps({
  id: {
    type: Number,
    required: true,
  },

  experienceSlug: {
    type: String,
    required: true,
  },
});

const experienceSlug = toRef(props, "experienceSlug");
const id = toRef(props, "id");

/**
 *  Find the destination that is equal to the right id
 */
const destination = computed(() => {
  return sourceData.destinations.find(
    (destination) => destination.id === id.value
  );
});

/**
 * Find the experience that is equal to the experienceSlug once we have
 * the right destination
 */
const experience = computed(() => {
  return destination.value.experiences.find(
    (experience) => experience.slug === experienceSlug.value
  );
});
</script>
