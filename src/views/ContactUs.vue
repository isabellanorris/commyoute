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
        ><v-card-text style="font-size: 30px; color: #ffffff"
          >Contact us</v-card-text
        ></v-card
      >
      <v-card color="#1F7087">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-office-building-marker</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Commyoute Limited, <br />
                  Danesfield House <br />
                  NL2 8BK <br />
                </div>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-email</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  hello@commyoute.co.uk
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
      <v-card color="#1F7087" dark
        ><v-card-text style="font-size: 30px; color: #ffffff"
          >Corporate packages</v-card-text
        ></v-card
      >
      <v-card color="#1F7087">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-office-building</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  We offer a range of corporate packages, which allow you to
                  invest directly in your employees wellbeing by creating a
                  bespoke Commyoute solution for your workforce. You can host or
                  sponsor classes for them, or encourage them to set up their
                  own - all while giving back to the charities you care about
                  most.
                  <br />
                  <br />Get in contact today, to help your employees commute
                  with their community!
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
      <v-card color="#1F7087" dark
        ><v-card-text style="font-size: 30px; color: #ffffff"
          >Don't just take our word for it! <br />
          <br />
          See what our supporters had to say:</v-card-text
        ></v-card
      >
      <v-card color="#1F7087">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <div style="padding: 0px 2px 5px 2px">
                  <br />Chris A: <br />
                  <br />
                  I love Commyoute! I've been using it for 6 months now, and
                  have learnt so much. My favourite session has been French with
                  Rita, which replaced my Monday evening commute. Merci
                  Commyoute!
                </div>
                <br />
                <br />
                <div style="padding: 0px 2px 5px 2px">
                  Tom Cat from Renting180: <br />
                  <br />
                  I was so thankful my company onboarded Commyoute to help with
                  working from home. I used to walk to work, and was missing out
                  on the regular exercise, and was struggling to get out of bed
                  and start my day positively. <br />
                  <br />
                  8am Zumba classes with Tash have been just what I needed, and
                  I love that we are supporting local charities too!
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </div>
  </v-app>
</template>

<script>
  // @ is an alias to /src

  export default {
    name: "ContactUs",
    components: {},
  };
</script>
