<template>
  <q-item
    clickable
    @click="toPage"
    class="full-width q-py-md"
  >
    <q-item-section
      v-if="icon"
      avatar
      class="flex flex-center q-pr-none"
    >
      <q-icon
        :name="icon"
        size=32px
        color=grey-7
      />
    </q-item-section>
    <q-tooltip
      v-if="tooltip !== ''"
      class="text-no-wrap no-scroll"
    >
      {{tooltip}}
    </q-tooltip>
  </q-item>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'EssentialLink',
  props: {
    slug: {
      type: String,
      default: '/',
    },
    icon: {
      type: String,
      default: '',
    },
    tooltip: {
      type: String,
      default: '',
    },
  },
  methods: {
    toPage() {
      this.$router.push(this.slug);
    },
  },
});
</script>
