<template>
    <section class="skills-container">
        <h4>Skills</h4>
            <ul v-for="skill in skills" class="skills-list">
                <li>{{skill}}</li>
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


