<script setup>

import SearchBar from "./components/SearchBar.vue";

</script>

<template>
  <h1>Is there a post credit scene?</h1>
  <div class="logo">
    <img src="./assets/food-potcorn.png" alt="logo" />
    <h2>MovieFinder</h2>
  </div>

  <div class="hide">
  </div>

  <SearchBar/>
  <section>
    <table>
      <thead>
        <tr>
          <th></th>
          <th>Movie</th>
          <th>Infos</th>
          <th>Post Credit Scene</th>
        </tr>
      </thead>
      <tbody>
        <tr class="row">
          <td><img src="./assets/images.jpeg" alt="avengers" /></td>
          <td class="titre">Avengers</td>
          <td><p>2023</p>
          <p>2h 23min</p>
          </td>
          <td>Yes</td>
        </tr>
        <tr class="row">
          <td><img src="./assets/images.jpeg" alt="avengers" /></td>
          <td class="titre">Avengers</td>
          <td><p>2023</p>
          <p>2h 23min</p>
          </td>
          <td>Yes</td>
        </tr>
        <tr class="row">
          <td><img src="./assets/images.jpeg" alt="avengers" /></td>
          <td class="titre">Avengers</td>
          <td><p>2023</p>
          <p>2h 23min</p>
          </td>
          <td>Yes</td>
        </tr>
        <tr class="row">
          <td><img src="./assets/images.jpeg" alt="avengers" /></td>
          <td class="titre">Avengers</td>
          <td><p>2023</p>
          <p>2h 23min</p>
          </td>
          <td>Yes</td>
        </tr>
        <tr class="row">
          <td><img src="./assets/images.jpeg" alt="avengers" /></td>
          <td class="titre">Avengers</td>
          <td><p>2023</p>
          <p>2h 23min</p>
          </td>
          <td>Yes</td>
        </tr>

      </tbody>
    </table>

    
    
  </section>
</template>
<script>

export default {
  name: 'App',
  components: {
    SearchBar
  },
  data() {
    return {
      movies: [],
      search: "",
    };
  },
  mounted() {
    fetch("https://api.themoviedb.org/3/movie/550?api_key=1f54bd990f1cdfb230adb312546d765d")
    .then(response => response.json())
    .then((data) => {
      this.movies = data.results;
      console.log(data);
    });
  },
  }
</script>

<style scoped>
.hide{
  height: 150px;
  width: 100vw;
  background-color: rgba(0, 0, 0, 1);
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
}
h1 {
  position: relative;
  margin-top: 150px;
  text-align: center;
  font-size: 50px;
  font-weight: bold;
  margin-bottom: 100px;
  z-index: 999 !important;
}

.logo {
  position: fixed;
  top: 24px;
  left: 24px;
  display: flex;
  margin-bottom: 50px;
z-index: 999;
}

.logo img {
  width: 80px;
  height: 80px;
  margin-right: 20px;
}
table{
  width: 180%;
  margin-left: -40%;
  border-collapse: separate;
  border-spacing: 0;
  margin-bottom: 50px;
}
thead{
  font-size: 20px;
  font-weight: bold;
  border-bottom: white solid 4px;
  position: sticky;
  top:100px;
  z-index: 1001;
}
th{
  padding: 10px 0;
  border-collapse: separate;
  border-spacing: 0;
  border-bottom: white solid 4px;


}
tr{
  padding: 15px 0;
  border-bottom: white solid 2px;
  font-size: 20px;
  text-align: center;
  vertical-align: middle;
}
td img{
  height: 150px;
  width: auto;
  object-fit: cover;
  margin-right: 20px;
}
.titre{
  text-align: left;
  font-size: 30px;
  font-weight: bold;
  padding-left: 20px;
}
.titre p{
}
td:nth-child(1){
  width: 50px;
}
td{
  border-bottom: white solid 2px;
}

.row{
  animation: fade 1s;
  animation-timeline: view();
}

@keyframes fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
  0% {
    opacity: 0.01;
  }
  25%{
    opacity: 0.01;
  }
  80% {
    opacity: 1;
  }
  100% {
    opacity: 1;
  }

}

</style>
