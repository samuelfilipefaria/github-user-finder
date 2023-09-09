<template lang="pug">
form.search-form(@submit.prevent="searchUser")
  input.search-box-input(type="text" placeholder="github username..." v-model="githubUsername")
  button.search-box-button
    i.las.la-search
</template>

<script>
export default {
  data() {
    return {
      githubUsername: "",
    }
  },
  name: 'SearchForm',
  props: {

  },
  methods: {
    searchUser() {
      console.log(this.githubUsername);
    }
  }
}
</script>

<style scoped>
::placeholder {
  color: #b1b1b1;
}

.search-form {
  text-align: center;
}

.search-box-input, .search-box-button {
  background-color: #FFF;
  outline: none;
  border: solid 3px #000;
  border-radius: 0px;
  height: 30px;
  -moz-box-sizing: content-box;
  -webkit-box-sizing: content-box;
  font-size: 20px;
  box-sizing: content-box;
}

.search-box-input {
  color: #000;
  width: 200px;
  padding-left: 10px;
  margin-right: 10px;
}

.search-box-button {
  font-weight: bold;
  color: #000;
  padding-left: 10px;
  padding-right: 10px;
  cursor: pointer;
}
</style>
