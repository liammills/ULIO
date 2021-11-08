<template>
  <q-layout view="lHh Lpr lFf">

    <q-drawer
      show-if-above
      bordered
      :width="80"
    >
      <q-list class="full-height q-py-md flex justify-between">
        <div>
          <div
            class="self-start full-width text-center q-py-lg"
            style="border-bottom: 1px solid #bbbbbbbb"
          >
            ULIO
          </div>
          <div class="q-mt-md">
            <EssentialLink
              v-for="(link, index) in essentialLinks"
              :key="index"
              v-bind="link"
              class="q-my-md"
            />
          </div>
        </div>
        <EssentialLink
          :icon="'person_outline'"
          :link="'https://www.google.com'"
          :tooltip="'Account settings'"
          class="self-end"
        />
      </q-list>
    </q-drawer>

    <q-page-container style="background-color: #F5F5F8">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue';

const linksList = [
  {
    tooltip: 'Menu book thing idk',
    icon: 'menu_book',
    link: 'https://quasar.dev',
  },
  {
    tooltip: 'Analytics',
    icon: 'show_chart',
    link: 'https://github.com/quasarframework',
  },
  {
    tooltip: 'Help',
    icon: 'help_outline',
    link: 'https://awesome.quasar.dev',
  },
];

import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
  },

  setup() {
    return {
      essentialLinks: linksList,
    };
  },
});
</script>
