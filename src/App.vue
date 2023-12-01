<template lang="pug">
div.app
  SearchForm(@userData="userData" @start="isLoading = true" @end="isLoading = false")
  UserCard(:photo="userPhoto" :name="userName")
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
    userPhoto() {
      return this.user.avatar_url ? this.user.avatar_url : 'https://uxwing.com/wp-content/themes/uxwing/download/brands-and-social-media/github-icon.png';
    },

    userName() {
      return this.user.name ? this.user.name : "User name here";
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
