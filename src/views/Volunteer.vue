<template>
  <v-app>
    <div class="home">
      <v-card color="#1F7087">
        <v-img
          alt="Commyoute Logo"
          src="../assets/Commyoute_tag_line.png"
        ></v-img
      ></v-card>
      <v-card color="#1F7087" dark
        ><v-card-text
          >If you would like to donate your time, fill in the below form and
          someone from Commyoute will be in contact to arrange the
          session!</v-card-text
        ></v-card
      >
    </div>
    <div id="form-wrapper" v-if="finish === false">
      <form>
        <v-text-field
          v-model="name"
          :error-messages="nameErrors"
          label="Name"
          dark
          required
          @input="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="email"
          :error-messages="emailErrors"
          label="E-mail"
          dark
          required
          @input="$v.email.$touch()"
          @blur="$v.email.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="session"
          :error-messages="sessionErrors"
          label="What session would you like to run?"
          dark
          required
          @input="$v.session.$touch()"
          @blur="$v.session.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="availablity"
          :error-messages="availablityErrors"
          label="When are you available?"
          dark
          required
          @input="$v.availablity.$touch()"
          @blur="$v.availablity.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="charge"
          :error-messages="chargeErrors"
          label="How much would you like to charge? (Average session price is £4)"
          prefix="£"
          dark
          required
          @input="$v.charge.$touch()"
          @blur="$v.charge.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="charity"
          :error-messages="charityErrors"
          label="Which charity would you like the proceeds to be donated to?"
          dark
          required
          @input="$v.charity.$touch()"
          @blur="$v.charity.$touch()"
        ></v-text-field>
        <v-checkbox
          v-model="checkbox"
          :error-messages="checkboxErrors"
          label="Do you agree to the T&Cs?"
          dark
          required
          @change="$v.checkbox.$touch()"
          @blur="$v.checkbox.$touch()"
        ></v-checkbox>
        <v-btn class="mr-4" @click="submit"> submit </v-btn>
        <v-btn @click="clear"> clear </v-btn>
      </form>
    </div>
    <div id="form-wrapper" v-if="finish === true">
      <v-card color="#1F7087" dark
        ><v-card-text>Thank you for your submission!</v-card-text></v-card
      >
      <v-btn @click="back"> Back </v-btn>
    </div>
  </v-app>
</template>

<script>
  import { validationMixin } from "vuelidate";
  import { required, maxLength, email } from "vuelidate/lib/validators";

  export default {
    name: "Volunteer",
    mixins: [validationMixin],
    validations: {
      name: { required, maxLength: maxLength(10) },
      email: { required, email },
      session: { required },
      availablity: { required },
      charge: { required },
      charity: { required },
      checkbox: {
        checked(val) {
          return val;
        },
      },
    },

    data: () => ({
      name: "",
      email: "",
      session: "",
      availablity: "",
      charge: "",
      charity: "",
      checkbox: false,
      finish: false,
    }),

    computed: {
      checkboxErrors() {
        const errors = [];
        if (!this.$v.checkbox.$dirty) return errors;
        !this.$v.checkbox.checked && errors.push("You must agree to continue!");
        return errors;
      },
      nameErrors() {
        const errors = [];
        if (!this.$v.name.$dirty) return errors;
        !this.$v.name.required && errors.push("Please enter your name");
        return errors;
      },
      emailErrors() {
        const errors = [];
        if (!this.$v.email.$dirty) return errors;
        !this.$v.email.email && errors.push("Must be valid e-mail address");
        !this.$v.email.required &&
          errors.push("Please enter your email address");
        return errors;
      },
      sessionErrors() {
        const errors = [];
        if (!this.$v.session.$dirty) return errors;
        !this.$v.session.required &&
          errors.push("Please enter what session you would like to run");
        return errors;
      },
      availablityErrors() {
        const errors = [];
        if (!this.$v.availablity.$dirty) return errors;
        !this.$v.availablity.required &&
          errors.push("Please enter your availability");
        return errors;
      },
      chargeErrors() {
        const errors = [];
        if (!this.$v.charge.$dirty) return errors;
        !this.$v.charge.required &&
          errors.push("Please enter how much you would like to charge");
        return errors;
      },
      charityErrors() {
        const errors = [];
        if (!this.$v.charity.$dirty) return errors;
        !this.$v.charity.required &&
          errors.push("Please enter which charity you would like to support");
        return errors;
      },
    },

    methods: {
      back() {
        this.$v.$reset();
        this.name = "";
        this.email = "";
        this.session = "";
        this.availablity = "";
        this.charge = "";
        this.charity = "";
        this.checkbox = false;
        this.finish = false;
      },
      submit() {
        this.$v.$touch();
        this.finish = true;
      },
      clear() {
        this.$v.$reset();
        this.name = "";
        this.email = "";
        this.session = "";
        this.availablity = "";
        this.charge = "";
        this.charity = "";
        this.checkbox = false;
        this.finish = false;
      },
    },
  };
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Oswald:wght@200;400&display=swap");
  #form-wrapper {
    font-family: "Oswald", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 10px;
  }
</style>
