<template lang="pug">
div.app
  img.header-image(src="./assets/github.svg")
  h1.title GitHub User Finder
  SearchForm(@userData="userData")
  UserCard(:photo="userPhoto" :name="userName")
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
      user: {}
    }
  },
  computed: {
    userPhoto() {
      return this.user.avatar_url ? this.user.avatar_url : undefined;
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
@import url('https://fonts.googleapis.com/css2?family=Indie+Flower&display=swap');

html, body {
  background-color: #FFF;
  color: #000;
  font-family: sans-serif;
}

.title {
  font-family: 'Indie Flower', cursive;
  text-align: center;
}

.header-image {
  width: 100px;
  height: 100px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
