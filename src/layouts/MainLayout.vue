<template>
  <q-layout view="lHh Lpr lFf">

    <q-drawer
      show-if-above
      bordered
      :width="91"
    >
      <q-list class="full-height q-py-md flex justify-between">
        <div>
          <div
            class="self-start full-width text-center cursor-pointer"
            style="border-bottom: 1px solid #bbbbbbbb"
            @click="$router.push('/')"
          >
            <img
              alt="ULIO logo"
              src="../../public/icons/favicon-128x128.png"
              style="width: 90px"
              type="image/svg+xml"
            >
          </div>
          <div class="q-mt-md">
            <EssentialLink
              v-for="(link, index) in essentialLinks"
              :key="index"
              v-bind="link"
            />
          </div>
        </div>
        <EssentialLink
          :icon="'person_outline'"
          :slug="'account'"
          :tooltip="'Account'"
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
    tooltip: 'My courses',
    icon: 'menu_book',
    slug: 'courses',
  },
  {
    tooltip: 'Analytics',
    icon: 'show_chart',
    slug: 'analytics',
  },
  {
    tooltip: 'Help',
    icon: 'help_outline',
    slug: 'help',
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
