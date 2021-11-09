<template>
  <div>
    <q-page
      class="fixed-center flex column justify-center q-gutter-xl items-center"
      style="padding: 0"
    >
      <span class="login-header">
        Sign up to ULIO creators
      </span>
      <div class="q-gutter-lg q-mb-md">
        <q-input class="input" standout v-model="firstName" label="First name" />
        <q-input class="input" standout v-model="lastName" label="Last name" />
        <q-input class="input" standout v-model="email" label="Email address" />
        <q-input class="input" standout v-model="password" label="Password" />
      </div>
      <q-btn
        v-ripple
        flat
        no-caps
        label="Create account"
        @click="$router.push('platform')"
        class="btn white-btn"
      />
    </q-page>
  </div>
</template>

<script>

export default {
  name: 'Login',
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      password: '',
    };
  },
};
</script>
