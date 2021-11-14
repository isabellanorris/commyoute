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
          >Use our online calculator to tell us about how you used to travel to
          work, and calculate your time and money savings, working from
          home.</v-card-text
        ></v-card
      >
    </div>
    <div id="form-wrapper">
      <form id="formcore">
        <v-select
          id="formselecttype"
          v-model="select"
          :error-messages="selectErrors"
          :items="travelitems"
          dark
          label="How did you travel?"
          required
          @input="$v.select.$touch()"
          @blur="$v.select.$touch()"
        ></v-select>
        <v-text-field
          v-model="spend"
          :error-messages="spendErrors"
          dark
          prefix="£"
          label="How much did it cost you to make one journey?"
          required
          @input="$v.spend.$touch()"
          @blur="$v.spend.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="time"
          :error-messages="timeErrors"
          dark
          label="How long did it take in minutes?"
          required
          @input="$v.time.$touch()"
          @blur="$v.time.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="distance"
          :error-messages="distanceErrors"
          dark
          label="How far did you travel in miles?"
          required
          @input="$v.distance.$touch()"
          @blur="$v.distance.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="days"
          :error-messages="daysErrors"
          dark
          label="How many days a week were you traveling, that you don't now?"
          required
          @input="$v.days.$touch()"
          @blur="$v.days.$touch()"
        ></v-text-field>
        <v-btn class="mr-4" @click="submit"> Calculate </v-btn>
        <v-btn @click="clear"> Clear </v-btn>
      </form>
      <div v-if="costcalculationreturn !== undefined">
        <br />
        <br />
        <p id="costreturn">{{ costcalculationreturn }}</p>
        <br />
        <p id="timereturn">{{ timecalculationreturn }}</p>
        <br />
        <p id="carbonreturn">{{ carboncalculationreturn }}</p>
        <v-btn class="mr-4" @click="gotosessions"> Repurpose your time </v-btn>
      </div>
    </div>
  </v-app>
</template>

<script>
  import { validationMixin } from "vuelidate";
  import { required } from "vuelidate/lib/validators";

  export default {
    mixins: [validationMixin],

    validations: {
      select: { required },
      spend: { required },
      time: { required },
      distance: { required },
      days: { required },
    },

    data: () => ({
      select: undefined,
      spend: undefined,
      time: undefined,
      distance: undefined,
      days: undefined,
      travelitems: ["Car", "Train", "Bus", "Walk"],
      costcalculationreturn: undefined,
      timecalculationreturn: undefined,
      carboncalculationreturn: undefined,
      coefficient: undefined,
    }),

    computed: {
      selectErrors() {
        const errors = [];
        if (!this.$v.select.$dirty) return errors;
        !this.$v.select.required && errors.push("Please select a travel type");
        return errors;
      },
      spendErrors() {
        const errors = [];
        if (!this.$v.select.$dirty) return errors;
        !this.$v.select.required &&
          errors.push("Please enter how much you spent");
        return errors;
      },
      distanceErrors() {
        const errors = [];
        if (!this.$v.select.$dirty) return errors;
        !this.$v.select.required &&
          errors.push("Please enter how far you traveled");
        return errors;
      },
      daysErrors() {
        const errors = [];
        if (!this.$v.select.$dirty) return errors;
        !this.$v.select.required &&
          errors.push("Please enter how often you traveled");
        return errors;
      },
      timeErrors() {
        const errors = [];
        if (!this.$v.select.$dirty) return errors;
        !this.$v.select.required &&
          errors.push("Please enter how long your commute took");
        return errors;
      },
    },

    methods: {
      gotosessions() {
        this.$router.push({ name: "Sessions" });
      },

      submit() {
        this.$v.$touch();
        if (this.select == "Car") {
          this.coefficient = 0.2;
        } else if (this.select == "Train") {
          this.coefficient = 0.1;
        } else if (this.select == "Bus") {
          this.coefficient = 0.1;
        } else {
          this.coefficient = 0;
        }
        this.costcalculationreturn =
          "You are saving £" +
          Math.round(this.spend * this.days * 4.34) +
          " a month on average not commuting to work!  This is £" +
          Math.round(this.spend * this.days * 4.34 * 12) +
          " a year, which is enough to buy " +
          Math.round((this.spend * this.days * 4.34 * 12) / 0.28) +
          " cherry bakewells!";
        this.timecalculationreturn =
          "You are saving " +
          Math.round(10 * ((this.time * this.days * 4.34 * 2) / 60)) / 10 +
          " hours a month not commuting to work! This is " +
          Math.round((this.time * this.days * 4.34 * 2 * 12) / 60) +
          " hours a year, which is enough time to learn " +
          (100 *
            Math.round(
              10 * ((this.time * this.days * 4.34 * 2 * 12) / 60 / 480)
            )) /
            10 +
          "% of a language!";
        this.carboncalculationreturn =
          "You are saving " +
          Math.round(this.coefficient * this.distance * this.days * 4.34 * 2) +
          " kg of CO2 a month not commuting to work!";
      },
      clear() {
        this.$v.$reset();
        this.spend = "";
        this.days = "";
        this.distance = "";
        this.select = null;
        this.time = "";
        this.costcalculationreturn = undefined;
      },
    },
  };
</script>

<style>
  #form-wrapper {
    font-family: "Oswald", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    background-color: #1f7087;
    padding: 10px;
  }
  #formcore {
    font-family: "Oswald", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    background-color: #1f7087;
    padding: 10px;
  }
</style>
