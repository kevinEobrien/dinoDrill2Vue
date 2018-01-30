<template>
    <section class="skills-container">
        <h4>Skills</h4>
            <ul class="skills-list">
                <li v-for="skill in skills"> {{skill}}</li>
            </ul>
    </section>
</template>
<script>
export default {
  name: "SkillList",
  props: {
    skills: {
    type: Array,
    required: true
    }
  }
}
</script>
<style scoped>
  .skills-list {
    list-style: none;
}
</style>


