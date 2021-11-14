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
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="text-h7"
                        v-text="session.name"
                      ></v-card-title>
                      <v-card-subtitle style="text-align: left"
                        ><a
                          style="color: white"
                          target="_blank"
                          :href="'http://' + session.organiser"
                        >
                          {{ session.organiser }}</a
                        >
                      </v-card-subtitle>
                      <v-card-text
                        class="body-1"
                        v-text="session.donation"
                        style="padding: 0px"
                      ></v-card-text>

                      <v-card-text
                        class="body-1"
                        v-text="session.avaliability"
                        style="padding: 0px"
                      ></v-card-text>
                    </div>
                    <v-avatar class="ma-3" size="120" tile>
                      <img
                        v-if="session.key == 'OneCan'"
                        src="@/assets/OneCan.png"
                      /><img
                        v-if="session.key == 'Macmillan'"
                        src="@/assets/Macmillan.jpg"
                      />
                      <img
                        v-if="session.key == 'Mind'"
                        src="@/assets/Mind.png"
                      />
                      <img
                        v-if="session.key == 'CBUK'"
                        src="@/assets/ChildBereavmentUK.png"
                      />
                      <img
                        v-if="session.key == 'WaterAid'"
                        src="@/assets/WaterAid.png"
                      />
                    </v-avatar>
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
    name: "Charity",
    data() {
      return {
        search: "",
        headers: [
          {
            text: "Session",
            align: "start",
            sortable: false,
            value: "name",
          },
          { text: "Organiser", value: "organiser" },
          { text: "Link", value: "link" },
        ],
        list_session: [
          {
            key: "OneCan",
            name: "One Can",
            organiser: "www.onecantrust.org.uk",
          },
          {
            key: "Mind",
            name: "Mind",
            organiser: "www.mind.org.uk",
          },
          {
            key: "Macmillan",
            name: "Macmillan Cancer Support",
            organiser: "www.macmillan.org.uk",
          },

          {
            key: "CBUK",
            name: "Child Bereavement UK",
            organiser: "www.childbereavementuk.org",
          },

          {
            key: "WaterAid",
            name: "WaterAid",
            organiser: "www.wateraid.org/uk",
          },
        ],
      };
    },
  };
</script>
