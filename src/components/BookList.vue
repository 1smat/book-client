<template>
  <div class="book" v-for="book in books" :key="book">
    <div><strong>Kitob nomi: </strong> {{ book.name }}</div>
    <div><strong>Sinfi: </strong> {{ book.class }}</div>
  </div>
</template>

<script>
export default {
  props: {
    books: {
      type: Array,
      required: true,
    },
  },
}
</script>

<style scoped>
.book {
  margin: 10px;
  padding: 14px;
  border: 1px solid white;
}
</style>
