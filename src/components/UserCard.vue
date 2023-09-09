<template lang="pug">
div.user-card
  img(:src="photo")
  h1 {{ name }}
</template>

<script>
export default {
  name: "UserCard",
  data() {
    return {
    }
  },
  props: {
    photo: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
  }
}
</script>

<style scoped>
.user-card {
  height: 400px;
  width: 300px;
  margin-top: 50px;
  border: solid 3px #000;
  border-radius: 0px;
  font-size: 10px;
  text-align: center;
  box-shadow:
  0px 69px 93px rgba(0, 0, 0, 0.21);
  margin-left: auto;
  margin-right: auto;
}

.user-card img {
  display: block;
  margin-top: 10px;
  margin-bottom: 50px;
  margin-left: auto;
  margin-right: auto;
  border-radius: 50%;
  width: 200px;
  height: 200px;
  object-fit: cover;
  box-shadow:
  2.8px 2.8px 2.2px rgba(0, 0, 0, 0.02),
  6.7px 6.7px 5.3px rgba(0, 0, 0, 0.028),
  12.5px 12.5px 10px rgba(0, 0, 0, 0.035),
  22.3px 22.3px 17.9px rgba(0, 0, 0, 0.042),
  41.8px 41.8px 33.4px rgba(0, 0, 0, 0.05),
  100px 100px 80px rgba(0, 0, 0, 0.07)
;
}
</style>