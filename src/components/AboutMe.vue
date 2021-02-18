<template>
  <div
    class="row wrap justify-center items-center content-center customContainer"
    id="about"
  >
    <div class="child content">
      <h3 class="q-my-none text-center">About Me</h3>
      <h5 class="q-my-sm">
        A coding girl in a beautiful city - Victoria, Canada.
      </h5>
      <p class="text-body1">
        Hi! Thanks for vistitng my website.
        <br />
        Triggering from curiosity, I engage in programming and become passionate
        about Tech.
        <br />
        By hard-working at school and self-studying, I get some experience in
        Front-end and Back-end frameworks, such as React, Vue and Django.
        <br />
        After graduation, I love to work in a tech company in Canada to learn
        more and improve my experience from new challenges and other people.
      </p>

      <div class="row wrap justify-around items-center content-center">
        <q-item v-for="item in buttons" :key="item.name">
          <q-btn
            :color="item.color"
            :icon="item.icon"
            :label="item.name"
            :href="item.url"
            type="a"
            target="__blank"
            rounded
          />
        </q-item>
      </div>
    </div>
    <div class="child"></div>
  </div>
</template>
<script>
export default {
  // name: 'ComponentName',
  data() {
    return {
      buttons: [
        {
          name: "LinkedIn",
          icon: "eva-linkedin-outline",
          url: "https://www.linkedin.com/in/jen-hoang/",
          color: "blue"
        }
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
.content {
  width: 40%;
  max-width: 600px;
}
</style>
