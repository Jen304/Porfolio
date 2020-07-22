<template>
  <q-layout view="hHh Lpr fFf">
    <q-header :elevated="isElevated" :class="headerClass" height-hint="100">
      <!-- layout for desktop -->
      <q-toolbar class="desktop-only">
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg" />
          </q-avatar>
          Jen Hoang
        </q-toolbar-title>
        <q-btn
          flat
          dense
          v-for="(item, i) in menuList"
          :key="i"
          :to="item.link"
          :label="item.title"
          class="q-px-md q-py-xs text-weight-bold"
        />
      </q-toolbar>
      <!-- layout for mobile -->
      <q-toolbar class="mobile-only">
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg" />
          </q-avatar>
          Jen Hoang
        </q-toolbar-title>
        <q-btn
          flat
          @click="drawerRight = !drawerRight"
          round
          dense
          icon="eva-menu-outline"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      side="right"
      v-model="drawerRight"
      :width="210"
      :breakpoint="500"
      elevated
      overlay
      content-class="bg-accent text-secondary text-weight-bold text-uppercase"
    >
      <q-list>
        <q-item-label header class="text-primary">
          Jen Hoang
        </q-item-label>
        <q-separator />
        <EssentialLink
          v-for="item in menuList"
          :key="item.title"
          v-bind="item"
        />
      </q-list>
    </q-drawer>
    <MainBanner />

    <q-page-container id="main-content" class="bg-secondary no-padding">
      <!-- This is where pages get injected -->
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import debounce from "lodash/debounce";
import EssentialLink from "components/EssentialLink";
import MainBanner from "components/MainBanner";

export default {
  // name: 'LayoutName',
  components: {
    EssentialLink: EssentialLink,
    MainBanner: MainBanner
  },
  data() {
    return {
      drawerRight: false,
      isElevated: false,
      headerClass: "text-accent q-py-md q-px-lg transparent",
      menuList: [
        { title: "Home", link: "/", icon: "eva-home-outline" },
        {
          title: "About",
          link: "/#about",
          icon: "eva-smiling-face-outline"
        },
        { title: "Skills", link: "/#skills", icon: "eva-bulb-outline" },
        {
          title: "Contact",
          link: "#contact",
          icon: "eva-message-square-outline"
        }
      ]
    };
  },
  methods: {
    // change the style of navbar when user scroll the page
    handleScroll() {
      if (window.scrollY > 200) {
        (this.isElevated = true), (this.headerClass = "text-primary bg-accent");
      } else {
        this.headerClass = "text-accent q-py-md q-px-lg transparent";
        this.isElevated = false;
      }
    }
  },

  created() {
    this.handleDebouncedScroll = debounce(this.handleScroll, 10);
    window.addEventListener("scroll", this.handleDebouncedScroll);
  },

  beforeDestroy() {
    window.removeEventListener("scroll", this.handleDebouncedScroll);
  }
};
</script>
<style lang="scss" scoped>
.no-padding {
  padding-top: 0;
}
</style>
