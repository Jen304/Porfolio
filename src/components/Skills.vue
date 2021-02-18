<template>
  <div class="bg-white customContainer q-pb-xl" id="skills">
    <h3 class="text-center q-ma-none">Skills</h3>
    <div v-for="(list, name) in skills" :key="name">
      <h4 class="text-center skill-title">{{ name }}</h4>
      <q-card class="my-card" v-for="(item, i) in list" :key="i">
        <q-card-section
          class="bg-primary row wrap justify-around items-center content-center"
        >
          <div v-for="(skill, j) in item" :key="j">
            <q-img
              :src="skill.logo"
              class="q-mt-auto skill-logo"
              :id="skill.name"
            />

            <h5 class="q-my-xs text-center">
              {{ skill.name }}
            </h5>
          </div>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      skills: {
        frontEnd: [
          [
            { name: "HTML", logo: "skills-icon/html.svg" },
            { name: "CSS", logo: "skills-icon/css.svg" },
            { name: "JavaScript", logo: "skills-icon/javascript.svg" }
          ],
          [
            { name: "React", logo: "skills-icon/react.svg" },
            { name: "Next", logo: "skills-icon/nextjs.svg" }
          ],
          [
            { name: "Vue", logo: "skills-icon/vue.svg" },
            { name: "Nuxt", logo: "skills-icon/nuxt.svg" }
          ]
        ],
        backEnd: [
          [
            { name: "Django", logo: "skills-icon/django.svg" },
            { name: "Flask", logo: "skills-icon/flask.svg" },
            { name: "Ruby on Rails", logo: "skills-icon/ruby-on-rails.png" }
          ],
          [{ name: "SQL" }, { name: "MongoDB" }]
        ]
      }
    };
  }
};
</script>
<style lang="scss" scoped>
.skill {
  display: inline;
}
.my-card {
  max-width: 900px;
  margin: 20px auto;
}
.skill-title {
  margin-bottom: 0.5em;
}
.skill-logo {
  height: 60px;
  width: 60px;
}
#Next {
  width: 100px;
}
#Nuxt {
  width: 80px;
}
</style>
