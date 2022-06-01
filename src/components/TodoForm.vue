<script setup>
import { ref } from "vue";
import { useTodoListStore } from "../stores/TodoListStore";

const todo = ref("");
// use Pinia store:
const store = useTodoListStore();

function addItemAndClear(item) {
  if (item.length === 0) {
    return;
  }
  // invokes function in the store:
  store.addTodo(item);
  todo.value = "";
}
</script>

<template>
  <form @submit.prevent="addItemAndClear(todo)">
    <input v-model="todo" type="text" /><button>Add</button>
  </form>
</template>

<style></style>
