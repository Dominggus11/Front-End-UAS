<template>
  <div>
    <v-container fluid class="instagram">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-card style="width: 100%">
            <h1 class="text-center pt-6 font-weight-light display-2">
              DEVELOPER
            </h1>
            <v-divider class="my-6"></v-divider>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-4">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <!-- <v-img src="~@/assets/img/Edward.png"></v-img> -->
                        <img  src="@/assets/img/Edward.png" alt="" style="width:10rem">
                    </div>
                    <div class="text--disabled text-uppercase text-h5 my-2">
                        Edward Sebastian
                    </div>
                    <v-btn
                        v-bind="size"
                        rounded
                        outlined
                        color="blue"
                        class="mt-6"
                    >
                        <a href=https://www.instagram.com/watt.18>Follow Me</a>
                    </v-btn>
                    
                  </v-card-text>
                  <v-divider
                        style="margin-right: -23px"
                        vertical
                        v-if="this.$vuetify.breakpoint.smAndUp"
                  ></v-divider>
                </div>
                <v-divider
                    class="mx-4"
                    v-if="!this.$vuetify.breakpoint.smAndUp"
                ></v-divider>
              </v-col>
              <v-col class="col-12 col-sm-6 col-md-4">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                      <img  src="@/assets/img/Roy Malau.png" alt="" style="width:10rem">
                    </div>
                    <div class="text--disabled text-uppercase text-h5 my-2">
                      Roy Dominggus
                    </div>

                    <v-btn
                      v-bind="size"
                      rounded
                      outlined
                      color="blue"
                      class="mt-6"
                    >
                      <a href="https://www.instagram.com/roynov11">Follow Me</a>
                    </v-btn>
                  </v-card-text>
                  <v-divider
                    style="margin-right: -23px"
                    vertical
                    v-if="this.$vuetify.breakpoint.mdAndUp"
                  ></v-divider>
                </div>
                <v-divider
                  class="mx-4"
                  v-if="!this.$vuetify.breakpoint.smAndUp"
                ></v-divider>
              </v-col>
              <v-col class="col-12 col-md-4">
                <v-divider
                  v-if="this.$vuetify.breakpoint.smOnly"
                  class="mx-4"
                ></v-divider>

                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                      <img  src="@/assets/img/Moreno.png" alt="" style="width:10rem">
                    </div>
                    <div class="text--disabled text-uppercase text-h5 my-2">
                      Alessandro Moreno
                    </div>

                    <v-btn
                      v-bind="size"
                      rounded
                      outlined
                      color="blue"
                      class="mt-6"
                    >
                      <a href=https://www.instagram.com/morenozoldyck>Follow Me</a>
                    </v-btn>
                  </v-card-text>
                </div>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<style scoped>
.v-card {
  width: 100%;
}

.keterangan {
  color: blue;
  text-align: start;
  max-width: 100px;
  margin: 0;
}
.flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}

footer {
  bottom: 0;
}
</style>
