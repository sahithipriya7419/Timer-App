<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>


<template>
  <div>
    <nav class="navbar navbar-dark bg-dark">
      <h1>Timer App</h1>
    </nav>
      <div>
        <button type="button" class="btn btn-info btn-lg" :time="time" @click="setTime">30 sec</button>
        <button type="button" class="btn btn-info btn-lg">60 sec</button>
        <button type="button" class="btn btn-info btn-lg">90 sec</button>
        <input type="search" id="search" placeholder="Enter">
        <select class="search-select" v-model="result">
            <option value="min" selected>Minutes</option>
            <option value="sec">Seconds</option>
        </select>
        <button class="button button-go">Go</button>
      </div>
      <h1 class="time">00:00</h1>
  </div>
</template>

<script>
export default {
  name: 'App',
  data()
  {
    return{
      result:"",
      time:""
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 0px;
}

.navbar{
  color:azure;
  text-align: center;
}

.btn{
  float: left;
  margin-top:40px;
  margin-left:50px;
  margin-right: 20px;
}

#search{
   margin: 100px;
   margin-top:45px;
   margin-right: 40px;
   border: 2px solid black;
   border-radius: 5px;
   padding:6px;
}

.search-select{
   padding:6px;
   margin-right: 30px;
   border: 2px solid black;
}

.button {
  background-color: #04AA6D;
  border: none;
  color: white;
  padding: 20px;
  text-align: center;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius:60%;
}

.time{
  font-size: 100px; 
}


</style>
