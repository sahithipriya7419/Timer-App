<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav> -->
  <div>
    <nav class="navbar">
      <p>Timer App</p>
    </nav>
      <div>
        <button type="button" class="btn btn-info btn-lg" @click="setTime(30,true)">30 sec</button>
        <button type="button" class="btn btn-info btn-lg" @click="setTime(60,true)">60 sec</button>
        <button type="button" class="btn btn-info btn-lg" @click="setTime(90,true)">90 sec</button>
        <input type="search" id="search" placeholder="Enter" v-model="time">
        <select class="search-select" v-model="result">
            <option value="" selected>Minutes</option>
            <option value="1">Seconds</option>
        </select>
        <button class="button button-go" @click="setTime(time,result)">Go</button>
      </div>
      <h1 class="time">{{minute.toString().length===1?('0'+minute):(minute)}}:{{second.toString().length===1?('0'+second):(second)}}</h1>
  </div>
  <!-- <router-view/> -->
</template>

<script>
export default {
  name: 'App',
  data()
  {
    return{
      result:"",
      time:0,
      minute:0,
      second:0
    }
  },
  methods:{
     setTime(time,seconds)
     {
      seconds = Boolean(seconds)
      console.log(time,seconds)
       if(seconds)
       {
         this.second = (time)%60
         this.minute = parseInt((time)/60)
       }
       else{
         this.minute = time
       }
       setInterval(()=>{
            if(this.second===0 && this.minute>0)
            {
                this.minute = this.minute-1;
                this.second = 60;
            }
            if(this.second>0)
            {
                this.second--;
            }
       },1000)

     }
  }
}
</script>

<style>

*{
   margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.navbar{
  color: black;
  font-size: 1.5rem;
  background-color: white;
  box-shadow: 0px 2.98256px 7.4564px rgba(0, 0, 0, 0.1);
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
  text-align: center; 
}


</style> 



<!-- <template>

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


</style> -->
