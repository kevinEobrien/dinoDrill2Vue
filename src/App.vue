<template>
  <div id="app">
    <TheHeader/>
    <main>
    <Profiles :dinos="listingData" :skills="skillsData"/>
    </main>
    <TheFooter/>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader"
import TheFooter from "./components/TheFooter"
import Profiles from "./components/Profiles"
import SkillList from "./components/SkillList"

export default {
  name: 'App',
  components: {
    TheHeader, TheFooter, Profiles, SkillList
  },
  methods: {
    getListings() {
      fetch(this.apiURL)
        .then(response => response.json())
        .then(response => {
          this.listingData = response
          })
        }
        
  },
  data(){
    return{
      apiURL: "../static/dinosaurs.json",
      listingData: []
    }
  },
  mounted(){
    this.getListings();
  }
}
</script>

<style>
html {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  /* grid-template-rows: 15% 75% 10%; */
  grid-row: 2/3;
}

section {
  padding: 0 20px 0 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, x100%);
  grid-gap: 10px;
  margin: 0 auto;
  width: 50%;
}

small {
  color: black;
  font-size: .5rem;
  margin-left: 10px;
}

p {
  font-size: .8rem;
}
</style>
