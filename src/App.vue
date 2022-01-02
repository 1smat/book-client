<template>
  <div class="app">
    <div class="left">
      <form @submit.prevent>
        <h1>Kitob qo'shish</h1>
        <input
          v-bind:value="bookName"
          @input="inputName"
          class="input"
          type="text"
          placeholder="Kitob nomi"
        />
        <input
          v-bind:value="bookClass"
          @input="inputClass"
          class="input"
          type="text"
          placeholder="Kitob sinfi"
        />
        <button class="addBtn" @click="addBook">Kitob qo'shish</button>
      </form>
      <div class="book" v-for="book in books" :key="book">
        <div><strong>Kitob nomi: </strong> {{ book.name }}</div>
        <div><strong>Sinfi: </strong> {{ book.class }}</div>
      </div>
    </div>
    <div class="right">
      <button @click="setTime">Show time</button>
      <div id="time">{{ time }}</div>
    </div>
  </div>
</template>

<script>
let today = new Date()
let timer = today.getHours() + ':' + today.getMinutes()

export default {
  data() {
    return {
      time: '',
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
    setTime() {
      this.time = timer
    },
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
.right {
  margin: 20px 0 0 20px;
}
.book {
  margin: 10px;
  padding: 14px;
  border: 1px solid white;
}
.input {
  margin: 14px;
}
</style>
