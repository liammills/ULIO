<template>
  <div>
    <q-page
      class="fixed-center flex column justify-center items-center"
      style="padding: 0"
    >
      <span
        v-if="signedUp"
        class="login-header"
      >
        Check your text messages to continue!
      </span>
      <div
        v-else
        class="fixed-center flex column justify-center q-gutter-xl items-center"
      >
        <span class="login-header">
          Sign up with your number to learn!
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
            type="tel"
            standout
            bg-color="transparent"
            :input-style="{ color: '#545454' }"
            v-model="phone"
            label="Phone number"
            hide-bottom-space
            :rules="[val => !!val || 'Field is required', isValidPhoneNumber]"
          />
          <q-select
            class="input"
            :options="languageOptions"
            standout
            bg-color="transparent"
            :input-style="{ color: '#545454' }"
            v-model="language"
            label="Primary language"
            hide-bottom-space
            :rules="[val => !!val || 'Field is required', isValidLanguage]"
          />
        </div>
        <q-btn
          v-ripple
          flat
          no-caps
          label="Sign up"
          @click="signUp"
          class="btn white-btn"
        />
      </div>
    </q-page>
  </div>
</template>

<script>

export default {
  name: 'SignUp',
  data() {
    return {
      firstName: '',
      lastName: '',
      phone: '',
      language: '',
      languageOptions: [
        'Arabic',
        'French',
        'Hindi',
        'Mandarin',
        'Spanish',
      ],
      signedUp: false,
    };
  },
  methods: {
    isValidFirstName() {
      return this.firstName.length > 0 || 'First name must not be empty';
    },
    isValidLastName() {
      return this.lastName.length > 0 || 'Last name must not be empty';
    },
    isValidPhoneNumber() {
      return (this.phone.length > 0) || 'Must be valid phone number';
    },
    isValidLanguage() {
      return this.language !== '' || 'Must choose a language';
    },
    isValid() {
      if (!this.isValidFirstName()) return false;
      if (!this.isValidLastName()) return false;
      if (!this.isValidPhoneNumber()) return false;
      if (!this.isValidLanguage()) return false;
      return true;
    },
    async signUp() {
      if (this.isValid()) {
        // Send twilio text message in their language
        this.$q.notify(`Welcome, ${this.firstName}!`);
        this.signedUp = true;
      } else this.$q.notify('Invalid form input');
    },
  },
};
</script>
