<template>
  <q-page class="container">
    <div class="flex justify-between items-center">
      <span class="header1">
        Hi Adrian 👋
      </span>
      <q-btn
        class="purpleBtn"
        label="Create New"
        no-caps
        icon="add"
        flat
      />
    </div>
    <div class="q-gutter-lg q-mt-xl">
      <q-card class="card">
        <q-card-section class="q-pa-none">
          <q-img
            alt="image"
            src="../assets/image2.png"
          />
        </q-card-section>
        <q-card-section>
          <div class="q-pa-sm">
            <div class="q-mb-md subtitle">
              <span class="q-mr-xs">
                Create your first course
              </span>
              <q-icon
                name="east"
                size="22px"
              />
            </div>
            <span class="para">
              Create a language course to help our community!
            </span>
          </div>
        </q-card-section>
      </q-card>
      <!-- <q-card class="card">
        Abc
      </q-card> -->
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
});
</script>
