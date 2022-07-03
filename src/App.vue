<template>
  <v-app id="app">
    <div id="main-content">
      <div id="top-bar">
        <!-- Top bar: 1/3 currency/points, 1/3 level, 1/3 rank up rewards  -->
        <v-row>
          <v-col cols="4" id="currency-box">
            <v-card>
              <v-card-text>
                <Currency />
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4" id="level-box">
            <v-card>
              <v-card-text><Level /></v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4" id="rankup-box">
            <v-card>
              <v-card-text><RankRewards /></v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <!-- 2nd bar: 2/3 is log terminal, 1/3 is something -->
        <v-row>
          <v-col cols="9" id="log-terminal-box">
            <v-card>
              <v-card-text></v-card-text>
            </v-card>
          </v-col>
          <v-col cols="3" id="something-box">
            <v-card>
              <v-card-text></v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </div>
      <!-- Main content -->
      <router-view />
    </div>

    <!-- Side bar for switching main content (deposits, craft/refine, research, scientists, boosts) -->
    <v-navigation-drawer id="sidebar" absolute permanent right width="30%">
    </v-navigation-drawer>
  </v-app>
</template>

<script>
import Currency from "./components/TopBar/Currency.vue";
import Level from "./components/TopBar/Level.vue";
import RankRewards from "./components/TopBar/RankRewards.vue";

export default {
  name: "App",

  components: {
    Currency,
    Level,
    RankRewards,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
html,
body {
  overflow: hidden !important;
  height: 100vh;
}
</style>

<style lang="scss" scoped>
#app {
  background-color: black;
  /* position: absolute; */
}

#top-bar {
  padding: 20px 40px;
  width: 70%;
}

#sidebar {
  background-color: #111;
}
</style>
