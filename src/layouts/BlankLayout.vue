<template>
  <q-layout class="gradient-bg">
    <img
      alt="ULIO logo"
      src="../assets/white-logo.png"
      style="width: 100px; position: absolute; top: 5%; left: 5%"
      class="cursor-pointer"
      @click="$router.push('/')"
      type="image/svg+xml"
    >
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'BlankLayout',
});
</script>
