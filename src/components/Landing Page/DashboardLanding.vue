<template>
  <v-main>
    <div>
      <v-app-bar dark app fixed>
        <v-btn to="/">
          <v-icon class="ma-2">mdi-domain</v-icon>
          <h2>Yasogami Hotel</h2>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn class="mark ma-1" to="/register">REGISTER</v-btn>
        <v-btn class="mark ma-1" to="/userlogin">LOGIN</v-btn>
      </v-app-bar>
    </div>

    <div>
      <v-parallax
        height="1000"
        dark
        src="https://images.unsplash.com/photo-1517840901100-8179e982acb7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
      >
        <v-row align="center" justify="center">
          <v-col class="text-center" cols="8"> </v-col>
        </v-row>
      </v-parallax>
    </div>
    <div class="fullheight">
      <router-view></router-view>
    </div>
  </v-main>
</template>
