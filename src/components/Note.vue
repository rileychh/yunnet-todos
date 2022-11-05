<script setup>
import { defineProps } from "vue";

const props = defineProps(["contents"]);
</script>

<template>
  <article>
    <p>{{ props.contents }}</p>
  </article>
</template>

<style scoped>
  article {
    width: 10rem;
    height: 10rem;
    background-color: #F3E779;
    padding: 1rem;
  }
</style>
