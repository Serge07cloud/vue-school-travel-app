<template>
  <div id="nav">
    <router-link id="logo" to="/">Vue school travel app</router-link>
    <router-link
      v-for="destination in destinations"
      :key="destination.id"
      :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }"
    >
      {{ destination.name }}
    </router-link>
  </div>
</template>

<script lang="ts" setup>
import sourceData from "../data.json";
import { ref } from "@vue/runtime-core";

const destinations = ref(sourceData.destinations);
</script>
