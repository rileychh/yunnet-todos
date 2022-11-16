<script setup>
import { ref } from "vue";
import Note from "./components/Note.vue";

const notes = ref([]);
const contents = ref("");

function addNote() {
  notes.value.push(contents.value);
  contents.value = "";
}
</script>

<template>
  <header>
    <h1>YunNet To-dos</h1>
  </header>

  <form class="card">
    <h2>新增一個待辦事項</h2>
    <input v-model="contents" id="contents" type="text" placeholder="內容..." />
    <button type="submit" @click.prevent="addNote">新增</button>
  </form>

  <main>
    <Note v-for="note in notes" v-bind:contents="note" />
  </main>
</template>

<style scoped>
header {
  background-color: lightgray;
  padding: 1rem;
}

h1 {
  font-size: 1.5rem;
  font-weight: bold;
}

h2 {
  font-size: 1.25rem;
  font-weight: bold;
}

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  width: min-content;
  margin: 0.5rem auto;
  padding: 1rem;
  border: 1px lightgray solid;
  border-radius: 0.25rem;
}

.card button {
  all: unset;
  cursor: pointer;
  color: #00aaff;
  align-self: flex-end; /* align to right */
}

main {
  display: flex;
  gap: 0.5rem;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
