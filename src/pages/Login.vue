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
        <q-input
          class="input"
          standout
          bg-color="transparent"
          :input-style="{ color: '#545454' }"
          v-model="firstName"
          label="First name"
          hide-bottom-space
          :rules="[val => !!val || 'Field is required', isValidFirstName]"
        />
        <q-input
          class="input"
          standout
          bg-color="transparent"
          :input-style="{ color: '#545454' }"
          v-model="lastName"
          label="Last name"
          hide-bottom-space
          :rules="[val => !!val || 'Field is required', isValidLastName]"
        />
        <q-input
          class="input"
          type="email"
          standout
          bg-color="transparent"
          :input-style="{ color: '#545454' }"
          v-model="email"
          label="Email address"
          hide-bottom-space
          :rules="[val => !!val || 'Field is required', isValidLastName]"
        />
        <q-input
          class="input"
          type="password"
          standout
          bg-color="transparent"
          :input-style="{ color: '#545454' }"
          v-model="password"
          label="Password"
          hide-bottom-space
          :rules="[val => !!val || 'Field is required', isValidLastName]"
        />
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
  methods: {
    isValidEmail() {
      // const emailPattern = /^(?=[a-zA-Z0-9@._%+-]{6,254}$)
      // [a-zA-Z0-9._%+-]{1,64}@(?:[a-zA-Z0-9-]{1,63}\.){1,8}[a-zA-Z]{2,63}$/;
      // if (this.email.length === 0) {
      //   return 'Field is required';
      // }
      // return emailPattern.test(this.email) || 'Invalid email';
      return this.email.length > 0 || 'Email must not be empty';
    },
    isValidFirstName() {
      return this.firstName.length > 0 || 'First name must not be empty';
    },
    isValidLastName() {
      return this.lastName.length > 0 || 'Last name must not be empty';
    },
    isValidPassword() {
      return this.password.length > 0 || 'Password must not be empty';
    },
  },
};
</script>
