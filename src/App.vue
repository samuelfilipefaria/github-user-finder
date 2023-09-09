<template lang="pug">
div.app
  SearchForm
  UserCard(photo="" name="")
</template>

<script>
import SearchForm from './components/SearchForm.vue'
import UserCard from './components/UserCard.vue'

export default {
  name: 'App',
  components: {
    SearchForm,
    UserCard
  }
}
</script>

<style>
html, body {
  background-color: #FFF;
  color: #000;
  font-family: sans-serif;
}
</style>
