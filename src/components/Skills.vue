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
              :id="skill.id"
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
        "Front-end": [
          [
            { name: "HTML", logo: "skills-icon/html.svg", id: "html" },
            { name: "CSS", logo: "skills-icon/css.svg", id: "css" },
            {
              name: "JavaScript",
              logo: "skills-icon/javascript.svg",
              id: "javascript"
            }
          ],
          [
            { name: "React", logo: "skills-icon/react.svg", id: "react" },
            { name: "Next", logo: "skills-icon/nextjs.svg", id: "next" }
          ],
          [
            { name: "Vue", logo: "skills-icon/vue.svg", id: "vue" },
            { name: "Nuxt", logo: "skills-icon/nuxt.svg", id: "nuxt" }
          ]
        ],
        "Back-end": [
          [
            { name: "Django", logo: "skills-icon/django.svg", id: "django" },
            { name: "Flask", logo: "skills-icon/flask.svg", id: "flask" },
            {
              name: "Ruby on Rails",
              logo: "skills-icon/ruby-on-rails.png",
              id: "rails"
            }
          ],
          [{ name: "SQL", logo: "skills-icon/sql.jpg", id: "sql" }]
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
  height: 50px;
  width: 50px;
}
#next {
  width: 100px;
}
#nuxt {
  width: 67px;
}
#django {
  width: 144px;
}
#flask {
  width: 40px;
}
#rails {
  width: 80px;
}
</style>
