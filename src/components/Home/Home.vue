<template>
    <div>
    <v-container fluid class="instagram">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-card style="width: 100%">
            <div class="carousel-item active">
                <div class="containerhome">
                    <img  src="~@/assets/img/hotelcool.jpg" alt="" style="width:100%">
                    <h1 class="centered">Yasogami Hotel</h1>
                    <p class="centerbotom" style="text-align: justify">For the sophisticated and experienced business and leisure traveler alike, who appreciates quality and wants a friendly and accessible hotel, Yasogami provides comfortable facilities and personalized service. Having welcomed and passionately served millions of domestic and overseas guests every month for more than two decades, has earned us an unrivaled reputation as the most trusted hotel in the Archipelago and one of the most trusted names in hospitality far beyond. As we grow and expand globally, we stay true to our values and create incredible guest experiences across our eclectic hotels. We have a variety of astonishing brand choices for every taste and budget.</p>
                </div>
            </div>
            <h1 class="text-center pt-6 font-weight-light display-2">
              At Your Service
            </h1>
            <v-divider class="my-6"></v-divider>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-4">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <img  src="~@/assets/img/kolam.jpg" alt="" style="width:100%">
                    </div>
                    <div class="text--disabled text-uppercase text-h5 my-2">
                      Swimming Pool
                    </div>
                    <p>Need refreshments? Then the beautiful outdoor swimming pool of Yasogami Hotel is all what you need!</p>
                    
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
                      <img  src="~@/assets/img/minum.jpg" alt="" style="width:100%">
                    </div>
                    <div class="text--disabled text-uppercase text-h5 my-2">
                      24/7 Service
                    </div>
                    <p>Waking up at night, feeling hungry but too lazy to buy something yourself? Don't worry! Yasogami Hotel service is ready anytime!</p>
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
                      <img  src="~@/assets/img/gym.jpg" alt="" style="width:90%">
                    </div>
                    <div class="text--disabled text-uppercase text-h5 my-2">
                      Fitness Center
                    </div>
                    <p>Stay healthy together with the Fitness Center of Yasogami Hotel. We will provide you all the latest fitness equipment to fulfill your workout session.</p>
                  </v-card-text>
                </div>
              </v-col>
            </v-row>
            
            <v-divider class="my-6"></v-divider>
            <h1 class="text-center pt-6 font-weight-light display-2">
              About Yasogami Hotel
            </h1>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-6">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <img  src="~@/assets/img/hotelext2.jpg" alt="" width="100%">
                    </div>
                    
                  </v-card-text>
                </div>
                <v-divider
                  class="mx-4"
                  v-if="!this.$vuetify.breakpoint.smAndUp"
                ></v-divider>
              </v-col>
              <v-col class="col-12 col-md-6">
                <v-divider
                  v-if="this.$vuetify.breakpoint.smOnly"
                  class="mx-4"
                ></v-divider>

                <div class="flex-center">
                  <v-card-text>
                    <p style="text-center">The Yasogami Hotel is located in Special Region of Yogyakarta. We offer Gym, free parking, a tennis court, a beautiful swimming pool, and a restaurant serving hearty cuisine. Each room at The Yasogami Hotel includes a private bathroom and hairdryer. Free tea and coffee is provided in each room, along with flat-screen cable TV and free Wi-Fi. and many other facilities.</p>
                  </v-card-text>
                </div>
              </v-col>
            </v-row>
            <v-divider class="my-6"></v-divider>
            <h1 class="text-center pt-6 font-weight-light display-2">
              Guest Feedback
            </h1>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-6">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <img  src="~@/assets/img/userratings1.jpg" alt="" width="100%">
                    </div>
                    <div class="text-h4 my-2">
                      Joko Widodo
                    </div>
                    <h4 class="card-text">Rating : ★★★★★</h4>
                    <p style="text-center">Hotel Yang sangat bagus. pelayanannya bagus, desain hotelnya keren, kamarnya luas dan nyaman, fasilitasnya lengkap, pemandangannya keren, dan makanannya enak</p>
                    
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
              <v-col class="col-12 col-md-6">
                <v-divider
                  v-if="this.$vuetify.breakpoint.smOnly"
                  class="mx-4"
                ></v-divider>

                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                      <img  src="~@/assets/img/userratings2.jpg" alt="" width="100%">
                    </div>
                    <div class="text-h4 my-2">
                      Elon Musk
                    </div>
                    <h4 class="card-text">Rating : ★★★★☆</h4>
                    <p style="text-center">This is a cool Hotel. I really like the design, the service is good, the food is tasty, the facility is over the top, the view is great, overall it's a nice hotel. I love Indonesia</p>
                  </v-card-text>
                </div>
              </v-col>
            </v-row>
            
            <h1 class="text-center pt-6 font-weight-light display-2">
              Our Gallery
            </h1>
            <v-divider class="my-6"></v-divider>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-4">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <img  src="~@/assets/img/kolam.jpg" alt="" style="width:100%">
                    </div>
                    
                  </v-card-text>
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
                      <img  src="~@/assets/img/minum.jpg" alt="" style="width:100%">
                    </div>
                  </v-card-text>
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
                      <img  src="~@/assets/img/kolam.jpg" alt="" style="width:100%">
                    </div>
                  </v-card-text>
                </div>
              </v-col>
            </v-row>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-4">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <img  src="~@/assets/img/minum.jpg" alt="" style="width:100%">
                    </div>
                    
                  </v-card-text>
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
                      <img  src="~@/assets/img/kolam.jpg" alt="" style="width:100%">
                    </div>
                  </v-card-text>
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
                      <img  src="~@/assets/img/minum.jpg" alt="" style="width:100%">
                    </div>
                  </v-card-text>
                </div>
              </v-col>
            </v-row>
            <v-row class="text-center">
              <v-col class="col-12 col-sm-6 col-md-4">
                <div class="flex-center">
                  <v-card-text>
                    <div class="flex-center">
                        <img  src="~@/assets/img/kolam.jpg" alt="" style="width:100%">
                    </div>
                    
                  </v-card-text>
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
                      <img  src="~@/assets/img/minum.jpg" alt="" style="width:100%">
                    </div>
                  </v-card-text>
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
                      <img  src="~@/assets/img/kolam.jpg" alt="" style="width:100%">
                    </div>
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
.containerhome {
  position: relative;
  text-align: center;
  color: white;
}
.centered {
  position: absolute;
  top: 60%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.tengah{
    left:50%
}
.centerbotom {
  position: absolute;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>

<script>
export default {
  data: () => ({
    icons: [
      {
        text: "mdi-facebook",
        link: "",
      },
      {
        text: "mdi-twitter",
        link: "",
      },
      {
        text: "mdi-linkedin",
        link: "",
      },
      {
        text: "mdi-instagram",
        link: "",
      },
    ],
  }),
};
</script>
