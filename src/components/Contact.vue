<template>
  <div class="bg-accent">
    <q-card
      class="bg-accent my-card text-primary customContainer1"
      id="contact"
      flat
    >
      <h3 class="text-center text-primary q-pa-xl q-ma-none">Contact me</h3>
      <q-card-section class="special-text">
        <div>
          <p
            v-for="contact in contactList"
            :key="contact.name"
            class="text-center"
          >
            {{ contact.name }} : {{ contact.content }}
          </p>
          <q-separator />
          <h5 class="text-primary">Social channel</h5>
          <div class="row wrap justify-around items-center content-center">
            <q-item v-for="channel in socialMedia" :key="channel.name">
              <q-btn
                :color="channel.color"
                :icon="channel.icon"
                :label="channel.name"
                :href="channel.url"
                type="a"
                target="__blank"
                rounded
              />
            </q-item>
          </div>
        </div>
      </q-card-section>
    </q-card>
    <q-separator />
    <p class="q-mb-none text-secondary text-center q-py-sm">
      Jen Hoang &copy; 2020
    </p>
  </div>
</template>

<script>
export default {
  // name: 'ComponentName',
  data() {
    return {
      contactList: [
        {
          name: "Email",
          content: "jenhoang304@gmail.com"
        },
        {
          name: "Phone number",
          content: "+1 (236) 882 5419"
        }
      ],
      socialMedia: [
        {
          name: "LinkedIn",
          icon: "eva-linkedin-outline",
          url: "https://www.linkedin.com/in/jen-hoang/",
          color: "blue"
        },
        {
          name: "Github",
          icon: "eva-github-outline",
          url: "https://github.com/Jen304",
          color: "grey darken-4"
        }
      ]
    };
  }
};
</script>
<style scoped>
.my-card {
  max-width: 500px;
  margin: auto;
}
</style>
