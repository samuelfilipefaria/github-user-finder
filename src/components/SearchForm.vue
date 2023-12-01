<template lang="pug">
form.search-form(@submit.prevent="searchUser")
  input.search-box-input(type="text" placeholder="github username..." v-model="githubUsername")
  button.search-box-button
    i.las.la-search
</template>

<script>
export default {
  name: 'SearchForm',
  data() {
    return {
      githubUsername: "",
      isLoading: false
    }
  },
  props: {

  },
  methods: {
    searchUser() {
      const URL = "https://api.github.com/users/";

      fetch(URL + this.githubUsername, { method: "GET" }).then((response) => {
        return response.json().then((hash) => {
          this.$emit("userData", hash);
        });
      }).catch((error) => {
        console.log("Deu erro -> " + error);
      })
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
  border: solid 1.5px #252525;
  border-radius: 10px;
  height: 30px;
  padding: 5px;
  -moz-box-sizing: content-box;
  -webkit-box-sizing: content-box;
  font-size: 20px;
  box-sizing: content-box;
}

.search-box-input {
  color: #252525;
  width: 400px;
  padding-left: 10px;
  margin-right: 10px;
}

.search-box-button {
  width: 30px;
  font-weight: bold;
  color: #252525;
  padding-left: 10px;
  padding-right: 10px;
  cursor: pointer;
}
</style>
