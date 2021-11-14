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
          style="
            padding-top: 0px;
            font-family: Arial, sans-serif;
            font-size: 18px;
          "
        >
          Turn your commute into you time! <br />
          <br />With more and more remote working, many of us are no longer
          spending the time and money we once did on commuting to work. <br />
          <br />Commyoute allows you to repurpose the time and money once spent
          on a crowded train into something you enjoy, whilst supporting
          charities important to you.</v-card-text
        ></v-card
      >

      <v-card color="#1F7087">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-white-balance-sunny</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Start or end the day positively with something different
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-home</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Break up working-from-home and home life
                </div>
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-account-group</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Learn new skills and meet new people
                </div>
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-charity</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">Support charities</div>
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-train</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Claim back your commute
                </div>
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="10" tile> </v-avatar>
                <div style="padding: 0px 2px 5px 2px">How it works:</div>
                <v-card-text
                  >Use our online <a href="/calculator">calculator</a> to
                  visualise how much time and money you are now saving working
                  from home, before browsing our range of volunteer led
                  <a href="/sessions">sessions</a> to see how you would rather
                  be spending it! <br />
                  <br />We offer varied daily sessions to start or end the
                  workday. You can
                  <a href="/volunteer">volunteer to run a session</a> or join as
                  a participant. <br />
                  <br />
                  Proceeds from every session are donated to the volunteer's
                  charity of choice. Alternatively, you can simply donate your
                  cost savings
                  <a href="/charities">directly to charity</a>.</v-card-text
                >
              </v-card>
            </v-col>
          </v-row>
        </v-container>
        <!-- <v-col cols="12">
        <v-row justify-center> -->
      </v-card>
    </div>
  </v-app>
</template>

<script>
  // @ is an alias to /src

  export default {
    name: "Home",
    components: {},
  };
</script>
