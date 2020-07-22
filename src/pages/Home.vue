<template>
  <q-page>
    <AboutMe />
    <Skills />
  </q-page>
</template>

<script>
import AboutMe from "../components/AboutMe";
import Skills from "../components/Skills";

export default {
  name: "Home",
  components: {
    AboutMe,
    Skills
  }
};
</script>
<style lang="scss" scoped></style>
