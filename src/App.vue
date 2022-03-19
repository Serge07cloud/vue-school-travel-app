<template>
  <TheNavigation></TheNavigation>
  <div class="container">
    <router-view></router-view>
  </div>
</template>

<script lang="ts" setup>
import TheNavigation from "./components/TheNavigation.vue";
</script>
