<template>
  <v-footer dark padless>
    <v-card
      color="#021b22"
      flat
      tile
      class="lighten-1 white--text text-center"
      width="100%"
    >
      <v-card-text class="text-lg-h6" color="#FFFFFF" @click="contactus">
        Contact Us
      </v-card-text>
      <v-card-text color="#FFFFFF"
        >© 2021 COMMYOUTE LIMITED. NO RIGHTS RESERVED. COMMYOUTE LIMITED IS NOT
        A REGISTERED COMPANY IN ENGLAND AND WALES, UNREGISTERED OFFICE
        DANESFIELD HOUSE.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text color="#FFFFFF">
        {{ new Date().getFullYear() }} — <strong>Commyoute</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
  export default {
    data: () => ({
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
    }),
    methods: {
      contactus() {
        this.$router.push({ name: "ContactUs" });
      },
    },
  };
</script>
