<template>
  <div>
    <q-page-container
      class="fixed-center flex column q-gutter-lg"
      style="padding: 0"
    >
      <span class="main-header">
        Easy language learning with ULIO.
      </span>
      <div
        class="flex row justify-around flex-grow"
        style="min-width: 900px; margin-top: 60px"
      >
        <q-btn
          v-ripple
          flat
          no-caps
          label="Learn a language"
          @click="$router.push('join')"
          class="btn outlined-btn"
        />
        <q-btn
          v-ripple
          flat
          no-caps
          label="Create a course"
          @click="$router.push('login')"
          class="btn full-btn"
        />
      </div>
    </q-page-container>
    <img
      alt="ULIO logo"
      src="../assets/donut.png"
      style="width: 400px; position: absolute; top: 0; right: 0"
      type="image/svg+xml"
    >
    <img
      alt="ULIO logo"
      src="../assets/4-circle.png"
      style="width: 350px; position: absolute; bottom: 0"
      type="image/svg+xml"
    >
  </div>
</template>

<script>

export default {
  name: 'Home',
};
</script>
