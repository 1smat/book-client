<template>
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
</template>

<script>
export default {}
</script>

<style>
.input {
  margin: 14px;
}
</style>
