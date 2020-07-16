<template>
  <q-page>
    <AboutMe />
    <Skills />
    <Contact />
  </q-page>
</template>

<script>
import AboutMe from "../components/AboutMe";
import Skills from "../components/Skills";
import Contact from "../components/Contact";
export default {
  name: "Home",
  components: {
    AboutMe,
    Skills,
    Contact
  }
};
</script>
<style lang="scss" scoped></style>
