<template>
  <div
    class="row wrap justify-around items-center content-center customContainer"
    id="about"
  >
    <div class="child">
      <h3 class="q-my-none">About Me</h3>
      <h5 class="q-my-sm">An aspiring full-stack developer</h5>
      <p>
        I am a passionate software engineer with x years of working experience.
        I built OSS tools for Kubernetes using GO. My tools help people to
        deploy their workloads in Kubernetes. Sometimes, I work on some fun
        projects such as writing a theme, etc.
      </p>
      <q-btn color="accent" text-color="primary" label="My LinkedIn" rounded />
    </div>
    <div class="child">
      <q-circular-progress
        show-value
        v-for="(item, i) in softSkills"
        :key="i"
        class="text-white q-ma-md"
        :value="item.value"
        size="130px"
        :thickness="0.2"
        :color="item.color"
        center-color="grey-8"
        track-color="transparent"
      >
        <h6 class="text-subtitle2 q-ma-md">{{ item.title }}</h6>
      </q-circular-progress>
    </div>
  </div>
</template>
<script>
export default {
  // name: 'ComponentName',
  data() {
    return {
      softSkills: [
        {
          title: "Commitment",
          value: 80,
          color: "orange"
        },
        {
          title: "Problem solver",
          value: 80,
          color: "blue"
        },
        {
          title: "Self-motivation",
          value: 80,
          color: "green"
        },
        {
          title: "Team work",
          value: 80,
          color: "grey"
        },
        {
          title: "Hard-working",
          value: 80,
          color: "yellow"
        },
        {
          title: "Communication",
          value: 80,
          color: "red"
        }
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
.child {
  width: 500px;
}
</style>
