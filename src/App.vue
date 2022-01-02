<template>
  <div class="app">
    <div>
      <book-form />
      <book-list v-bind:books="books" />
    </div>
    <time-clock />
  </div>
</template>

<script>
import BookForm from '@/components/BookForm.vue'
import BookList from '@/components/BookList.vue'
import TimeClock from '@/components/TimeClock.vue'

export default {
  components: {
    BookForm,
    BookList,
    TimeClock,
  },
  data() {
    return {
      books: [
        {
          name: 'Matematika',
          class: 5,
        },
        {
          name: 'Fizika',
          class: 5,
        },
        {
          name: 'Tarix',
          class: '5',
        },
      ],
      bookName: '',
      bookClass: '',
    }
  },
  methods: {
    inputName(event) {
      this.bookName = event.target.value
    },
    inputClass(event) {
      this.bookClass = event.target.value
    },
    addBook() {
      const newBook = {
        id: Date.now(),
        name: this.bookName,
        class: this.bookClass,
      }
      this.books.push(newBook)
      this.bookName = ''
      this.bookClass = ''
    },
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  display: flex;
  justify-content: space-evenly;
  margin: 20px;
}
</style>
