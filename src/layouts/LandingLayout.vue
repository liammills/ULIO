<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="header bg-transparent text-black">
      <q-toolbar class="q-px-xl q-gutter-xl">
        <img
          alt="ULIO logo"
          src="../../public/icons/favicon-128x128.png"
          style="width: 90px"
          class="cursor-pointer"
          type="image/svg+xml"
        >
        <div
          v-for="(link, index) in navLinks"
          :key="index"
        >
          <span class="nav-link cursor-pointer">
            {{link.name}}
          </span>
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container class="content">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MainLayout',
  data() {
    return {
      navLinks: [
        {
          name: 'Home',
          slug: 'home',
        },
        {
          name: 'About Us',
          slug: 'about',
        },
        {
          name: 'Features',
          slug: 'features',
        },
        {
          name: 'Contact Us',
          slug: 'contact',
        },
      ],
    };
  },
  computed: {
    code() {
      return this.$store.state.game.gameCode;
    },
    username() {
      return this.$store.state.login.username;
    },
  },
});
</script>
