<template>
  <div class="bg-white customContainer q-pb-xl" id="skills">
    <h3 class="text-center">Skills</h3>
    <div>
      <h4 class="text-center skill-title">Front-end</h4>
      <q-card class="my-card" v-for="(item, i) in frontEnd" :key="i">
        <q-card-section
          class="bg-primary row wrap justify-around items-center content-center"
        >
          <h5 class="q-my-xs" v-for="(skill, j) in item" :key="j">
            {{ skill.name }}
          </h5>
        </q-card-section>
      </q-card>
    </div>
    <div>
      <h4 class="text-center skill-title">Back-end</h4>
      <q-card class="my-card" v-for="(item, i) in backEnd" :key="i">
        <q-card-section
          class="bg-primary row wrap justify-around items-center content-center"
        >
          <h5 class="q-my-xs" v-for="(skill, j) in item" :key="j">
            {{ skill.name }}
          </h5>
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
      frontEnd: [
        [
          { name: "HTML" },
          { name: "CSS" },
          { name: "SCSS" },
          { name: "JavaScript" }
        ],
        [{ name: "React" }, { name: "Vue" }, { name: "Nuxt" }]
      ],
      backEnd: [
        [{ name: "Ruby on Rails" }, { name: "Django" }, { name: "Firebase" }],
        [{ name: "SQL" }, { name: "Firestore" }]
      ]
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
</style>
