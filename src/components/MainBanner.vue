<template>
  <q-banner class="custom-banner text-white text-center relative-position">
    <div>
      <h1 class="title">Hi, I'm Jen!</h1>
      <h4>
        <vue-typer
          :text="aboutMe"
          :repeat="Infinity"
          :shuffle="false"
          initial-action="erasing"
          :pre-type-delay="50"
          :type-delay="50"
          :pre-erase-delay="2000"
          :erase-delay="250"
          erase-style="backspace"
          :erase-on-complete="false"
          caret-animation="smooth"
        ></vue-typer>
      </h4>
    </div>
    <!-- Wrapping only one DOM element, defined by QBtn -->
    <div class="absolute-bottom">
      <div :class="classes" @mouseover="hoverOver" @mouseout="hoverOut">
        <q-btn
          flat
          round
          icon="eva-arrowhead-down-outline"
          style="font-size: 25px;"
          class="text-accent text-weight-bold"
          to="#main-content"
        />
      </div>
    </div>
  </q-banner>
</template>

<script>
import { VueTyper } from "vue-typer";
export default {
  // name: 'ComponentName',
  components: {
    "vue-typer": VueTyper
  },
  data() {
    return {
      aboutMe: [
        "I'm a full-stack developer.",
        "I love coding!",
        "I love challenges!"
      ],
      classes: "animated bounce"
    };
  },
  methods: {
    hoverOver() {
      setTimeout(() => {
        this.classes = ["animated", "bounce"];
      }, 1000);
    },

    hoverOut() {
      setTimeout(() => {
        this.classes = [];
      }, 1000);
    }
  }
};
</script>
<style lang="scss">
.custom-banner {
  background: url("~assets/banner.png");
  background-position: center;
  background-size: 100% 100%;
  height: 100vh;
}
</style>
