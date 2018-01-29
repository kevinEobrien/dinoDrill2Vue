<template>
    <section id="profiles-container">
        <h2>Profiles</h2>
        <ul v-for="dino in dinos" id="profiles">
            <li>
                <div class="profile-card" @click="skillsToggle = !skillsToggle">
                    <header class="profile-header">
                        <img v-bind:src="dino.image" />
                        <h2>{{dino.name}}</h2>
                    </header>
                    <section class = skills-container :class="{ hidden : skillsToggle }">
                    <SkillList :skills="dino.skills"/>
                    </section>
                </div>
        </li>
    </ul>
    </section>
</template>
<script>
import SkillList from "./SkillList"
export default {
  name: "Profiles",
components:{SkillList
    },
props:["dinos", "skills"]
, 
methods:{
    unhide(){
        console.log("It runs")
        
        }
    },
    data () {
    return {
      skillsToggle: true
    }
}
}
</script>
<style scoped>
.profile-card {
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  padding: 10px;
  /* margin: 0 auto 10px auto; */
}
h2{
    text-align:start;
}

.profile-header {
  display: flex;
  flex-flow: row nowrap;
}

.profile-header img {
  width: 100px;
  height: 100px;
  border: 1px solid darkgrey;
  margin: 0 10px 0 10px;
}

 .hidden {
   display: none;
}
</style>

