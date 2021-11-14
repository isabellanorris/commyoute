<template>
  <div id="table">
    <v-card>
      <v-card-title>
        <v-spacer></v-spacer>
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          single-line
          hide-details
        ></v-text-field>
      </v-card-title>
      <v-app>
        <v-card>
          <v-container>
            <v-row>
              <v-col cols="12" v-for="(session, i) in list_session" :key="i">
                <v-card color="#1F7087" dark>
                  <div class="d-flex justify-space-between">
                    <v-avatar class="ma-3" size="120" tile>
                      <img
                        v-if="session.key == 'Knit'"
                        src="@/assets/chick.jpg"
                      /><img
                        v-if="session.key == 'Dance'"
                        src="@/assets/swingjpg.jpg"
                      />
                      <img
                        v-if="session.key == 'Cook'"
                        src="@/assets/fruit.jpg"
                      />
                      <img
                        v-if="session.key == 'Hebrew'"
                        src="@/assets/afeph.jpg"
                      />
                      <img v-if="session.key == 'Cat'" src="@/assets/Raj.jpg" />
                      <img
                        v-if="session.key == 'Spin'"
                        src="@/assets/bike.png"
                      />
                      <img
                        v-if="session.key == 'Code'"
                        src="@/assets/code.jpg"
                      />
                         <img
                        v-if="session.key == 'Singing'"
                        src="@/assets/singing.jpg"
                      />
                    </v-avatar>
                    <v-container fill-width fluid>
                      <v-row justify="center">
                        <v-card-text
                          class="text-h6" font-family="sans-serif;"
                          v-text="session.name"
                          style="padding: 5px"
                        ></v-card-text>
                        <v-card-text
                          v-text="session.organiser"
                          style="padding: 3px"
                        ></v-card-text>
                        <v-card-text
                          class="body-1"
                          v-text="session.donation"
                          style="padding: 3px"
                        ></v-card-text>
                        <v-card-text
                          class="body-1"
                          v-text="session.avaliability"
                          style="padding: 3px"
                        ></v-card-text>
                      </v-row>
                    </v-container>
                  </div>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-app>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Sessions",
  data() {
    return {
      search: "",
      headers: [
        {
          align: "start",
          sortable: false,
          value: "name",
        },
        { text: "Organiser", value: "organiser" },
        { text: "Donation", value: "donation" },
        { text: "Availability", value: "avaliability" },
      ],
      list_session: [
        {
          key: "Knit",
          name: "Knitting Workshop",
          donation: "£5.50",
          organiser: "with: Jess",
          avaliability: "Mondays 8am",
        },
        {
          key: "Cook",
          name: "Online Cooking Class",
          donation: "£3.50",
          organiser: "with: Feyaaz",
          avaliability: "Thursdays 5:30pm",
        },
        {
          key: "Dance",
          name: "Dance Class",
          donation: "£6.50",
          organiser: "with: Rob",
          avaliability: "Wednesday 8am",
        },
{
          key: "Singing",
          name: "Learn to sing",
          donation: "£6.50",
          organiser: "with: Bella",
          avaliability: "Fridays 8am",
        },
        {
          key: "Hebrew",
          name: "Intro to Hebrew",
          donation: "£1.50",
          organiser: "with: Shiri",
          avaliability: "Thursday 6pm",
        },

        {
          key: "Cat",
          name: "Why do cats sit in boxes?",
          donation: "£2.50",
          organiser: "with: Rebecca",
          avaliability: "Any day 8am",
        },
        {
          key: "Code",
          name: "Intro to Python",
          donation: "£2.50",
          organiser: "with: Jaime",
          avaliability: "Mondays 8am",
        },
        {
          key: "Spin",
          name: "Spin Class",
          donation: "£4.50",
          organiser: "with: Rita",
          avaliability: "Wednesdays at 6pm",
        },
      ],
    };
  },
};
</script>


