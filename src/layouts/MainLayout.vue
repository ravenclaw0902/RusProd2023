<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleMainMenu"
        />
      </q-toolbar>
      <q-logo> </q-logo>
    </q-header>

    <q-dialog v-model="mainMenu" show-if-above bordered>
      <q-card class="q-dialog-plugin">
        <q-list>
          <EssentialLink
            v-for="link in essentialLinks"
            :key="link.title"
            v-bind="link"
          />
        </q-list>
      </q-card>
    </q-dialog>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer>
      <q-item class="footer-1" aria-label="Menu">
        <FooterLink
          v-for="link in footerLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-item>
      <q-item class="footer-2"> </q-item>
      <q-item class="footer-3">&copy; АО "РУССКИЙ ПРОДУКТ", 2023</q-item>
    </q-footer>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import FooterLink from "components/FooterLink.vue";

const linksList = [
  {
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
    FooterLink,
  },

  setup() {
    const mainMenu = ref(false);

    return {
      essentialLinks: linksList,
      mainMenu,
      toggleMainMenu() {
        mainMenu.value = !mainMenu.value;
      },
      footerLinks: linksList,
    };
  },
});
</script>
