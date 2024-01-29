<template>
  <input type="text" placeholder="Search for a movie" />
</template>
<script>
export default {
  name: 'SearchBar'
}
</script>
<style scoped>label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
}

input[type="text"] {
  color: black;
  padding: 10px 5%;
  font-size: 24px;
  border-radius: 25px;
  width: 90%;
  height: 36px;
  margin-bottom: 100px;
  background-color: white;
  transition: all 0.30s ease-in-out;
  border: none;
  font-weight: bold;
  position : sticky;
  top: 24px;
  z-index: 999;
}

input[type="text"]:focus {
  color: white;
  border-color: white;
  box-shadow: 0 0 10px white;
  outline: none;
  background: none;
  transition: all 0.30s ease-in-out;
}

img {
  width: 30px;
  height: 30px;
  object-fit: cover;
  transform: translate(250px, -60px);
}

input[type="text"]:focus + img {
  transform: translate(250px, -60px) scale(1.3);
  transition: all 0.30s ease-in-out;
}
</style>