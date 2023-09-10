<template lang="pug">
div.app
  SearchForm(@userData="userData" @start="isLoading = true" @end="isLoading = false")
  UserCard(v-if="isUserLoaded" :photo="user.avatar_url" :name="user.name")
  h1(v-if="isLoading") Carregando...
</template>

<script>
import SearchForm from './components/SearchForm.vue'
import UserCard from './components/UserCard.vue'

export default {
  name: 'App',
  components: {
    SearchForm,
    UserCard
  },
  data() {
    return {
      user: {},
      isLoading: false
    }
  },
  computed: {
    isUserLoaded() {
      return Object.keys(this.user).length != 0;
    }
  },
  methods: {
    userData(hash) {
      this.user = hash;
    }
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
