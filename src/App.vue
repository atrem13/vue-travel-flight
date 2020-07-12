<template>
  <v-app id="app">
    <!-- <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.text"
          link
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              {{ item.text }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-subheader class="mt-4 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
        <v-list>
          <v-list-item
            v-for="item in items2"
            :key="item.text"
            link
          >
            <v-list-item-avatar>
              <img
                :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`"
                alt=""
              >
            </v-list-item-avatar>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item>
        </v-list>
        <v-list-item
          class="mt-4"
          link
        >
          <v-list-item-action>
            <v-icon color="grey darken-1">mdi-plus-circle-outline</v-icon>
          </v-list-item-action>
          <v-list-item-title class="grey--text text--darken-1">Browse Channels</v-list-item-title>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon color="grey darken-1">mdi-cog</v-icon>
          </v-list-item-action>
          <v-list-item-title class="grey--text text--darken-1">Manage Subscriptions</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->

    <!-- navbar -->
    <v-app-bar
      app
      clipped-left
      color="white"
      dense
      class="indigo--text mb-0">
      <!-- <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon> -->
      <v-icon
        class="mx-4"
        large
        color="indigo"
      >
        flight_takeoff
      </v-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">Flight Travel</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-row
        align="right"
        style="max-width: 650px"
      >
        <v-btn 
          text 
          v-for="link in links" 
          :key="link.text" 
          router 
          :to="link.route"
          color="indigo"
        >
          {{link.text}}
        </v-btn>
      </v-row>
    </v-app-bar>
    <!-- end navbar -->

    <!-- banner -->
    <v-container class="ma-0 pa-0" fluid>
      <v-parallax height="697" src="banner/simon-migaj-Yui5vfKHuzs-unsplash.jpg" class="ma-0 pa-0">
        <!-- <v-card color="rgb(0,0,0,.5)" height="100%">
        </v-card> -->
        <v-container>
          <v-row
            class="mt-5"
            align="center"
            justify="center"
          >
            <v-col class="mt-5 text-left" cols="12">
              <div class="text-h4 font-weight-bold">Flight Deal</div>
              <div class="text-subtitle-1">Kuwait - Dubai</div>
              <div class="text-h4">
                <v-btn depressed x-small color="red darken-4" class="white--text">
                  KWD
                </v-btn>
                <span class="ml-3 font-weight-bold pt-5">26.50</span>
              </div>
              <div class="mt-3">
                <v-btn depressed small rounded color="yellow darken-2 white--text">Book Now</v-btn>
              </div>

            </v-col>
          </v-row>
        </v-container>
      </v-parallax>
    </v-container>
    <!-- end banner -->

    <!-- flight plan -->
    <v-container>
      <v-card rounded outlined>
        <v-layout row wrap class="px-5 py-3 mx-5">
          <v-flex xs12 sm4 md2>
            <div class="subtitle-1">Find your flight</div>
            <v-radio-group v-model="radioGroup">
              <v-radio
                v-for="item in flightOptions"
                :key="item.title"
                :label="item.text"
                :value="item.text"
              ></v-radio>
            </v-radio-group>
          </v-flex>
          <v-flex xs12 sm12 md10>
            <v-card class="mt-5">
              <v-layout row wrap class="px-5 py-3 mx-5">
                <v-flex xs4>
                  <v-select
                    :items="destinations"
                    menu-props="auto"
                    hide-details
                    label="From"
                    single-line
                  ></v-select>  
                </v-flex>
                <v-flex xs4>
                  <v-select
                    :items="destinations"
                    menu-props="auto"
                    hide-details
                    label="To"
                    single-line
                  ></v-select>   
                </v-flex>
                <v-flex xs4>
                  <v-layout row wrap class="px-5">
                    <v-flex xs6>
                      <v-select
                        :items="destinations"
                        menu-props="auto"
                        hide-details
                        label="Depature"
                        single-line
                      ></v-select>   
                    </v-flex>
                    <v-flex xs6>
                      <v-select
                        :items="destinations"
                        menu-props="auto"
                        hide-details
                        label="Return"
                        single-line
                      ></v-select>   
                    </v-flex>
                  </v-layout>
                </v-flex>
                <v-flex xs4>
                  <v-select
                    :items="destinations"
                    menu-props="auto"
                    hide-details
                    label="Passenger & Class"
                    single-line
                  ></v-select>  
                </v-flex>
                <v-flex xs4>
                  <v-select
                    :items="destinations"
                    menu-props="auto"
                    hide-details
                    label="Prefered Airline"
                    single-line
                  ></v-select>   
                </v-flex>
                <v-flex xs4>
                  <v-layout row wrap class="px-5">
                    <v-flex xs12>
                      <v-checkbox class="mx-2" label="Non Stop"></v-checkbox> 
                    </v-flex>
                  </v-layout>
                </v-flex>
              </v-layout>
            </v-card>
          </v-flex>
          <v-flex xs6 sm6 md2>
            <v-layout row wrap>
             
            </v-layout>
          </v-flex>
        </v-layout>
      </v-card>
      <v-layout mt-5>
        <v-flex xs12>
          <p>
            Top Search: 
            <v-chip
              class="ma-2"
            >
              Default
            </v-chip>
            <v-chip
              class="ma-2"
            >
              Default
            </v-chip>
            <v-chip
              class="ma-2"
            >
              Default
            </v-chip>
          </p>
        </v-flex>
      </v-layout>
    </v-container>

    <!-- special flight deal -->
    <v-container class="mb-5">
      <v-sheet
        class="mx-auto"
        elevation="8"
        max-width="100%"
        outlined
      >
        <v-slide-group
          v-model="model"
          class="pa-4"
          active-class="success"
          show-arrows
        >
          <v-slide-item
            v-for="n in 15"
            :key="n"
            v-slot:default="{ active, toggle }"
          >
            <v-card
              :color="active ? 'grey lighten-5' : 'white'"
              class="ma-4"
              width="250"
              @click="toggle"
            >
              <v-img
                class="white--text align-end"
                height="150px"
                src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
              >
                <!-- <v-card-title>Top 10 Australian beaches</v-card-title> -->
              </v-img>

              <v-card-text class="text--primary">
                <div class="mb-3">
                  <v-icon left color="yellow">flight_takeoff</v-icon>
                  Kuwait  
                </div>
                <div class="mb-3">
                  <v-icon left color="yellow">flight_land</v-icon>
                  Dubai 
                </div>
                <v-divider></v-divider>
                <div class="mt-3">
                  Starting from KWD 26.50
                </div>
              </v-card-text>

              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  color="blue"
                  text
                >
                  Detail
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
    </v-container> 

    <!-- get best deal banner -->
    <v-container fluid class="ma-0 pa-0">
      <v-parallax
        src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
      >
        <v-row
          align="center"
          justify="center"
        >
          <v-col class="text-center" cols="5">
            <h1 class="text-h4 font-weight-bold mb-4">Get the best deals</h1>
            <h4 class="subheading grey--text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa quos eum rem totam iusto facere, amet eius inventore. </h4>
            <p class="text-body-1 mt-5 font-weight-bold">100% price transparant | Trusted and free</p>
            <v-btn 
              class="mt-5"
              color="warning"
              rounded>
              Book Now
            </v-btn>
          </v-col>
        </v-row>
      </v-parallax>
    </v-container>

    <!-- special hot deal -->
    <v-container class="mt-5">
      <v-layout row wrap>
        <v-flex xs10 offset-1>
          <v-layout row wrap>
            <v-flex xs3 class="pa-5" v-for="(n, i) in 4" :key="i">
              <v-card
                  class=""
                >
                  <v-img
                    class="white--text align-end"
                    height="150px"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <!-- <v-card-title>Top 10 Australian beaches</v-card-title> -->
                  </v-img>

                  <v-card-text>
                    <p class="">
                      Rove Dubai Maria
                    </p>
                    <h3>Dubai</h3>
                    <p>Starting from</p>
                    <p>KWD 45.50</p>
                  </v-card-text>
                  <v-card-actions>
                    <v-btn
                      text
                      color="primary"
                    >
                    See Detail
                    </v-btn>
                  </v-card-actions>
                </v-card>
            </v-flex>
          </v-layout>
        </v-flex>
      </v-layout>
    </v-container>

    <!-- subscribe to news letter -->
     <v-container>
       <v-row wrap>
         <v-col xs="10" offset="1">
            <v-row wrap>
              <v-col
                xs="5"
                md="5"
                sm="5"
              >
                <h3>
                  Subscribe <br>
                  To Our NewsLetter
                </h3>

              </v-col>
              <v-col
                xs="6"
                sm="6"
                md="6"
              >
                <v-text-field 
                  type="text" 
                  label="Email" 
                  prepend-icon="email"  
                  v-model="email" 
                >
                </v-text-field>
                
              </v-col>
            </v-row>
         </v-col>
       </v-row>
     </v-container>

     <!-- footer -->
      <v-container>
         <v-row>
           <v-col 
            xs="12"
            sm="4"
            md="4"
           >
            <h3>About Us</h3>
            <p class="text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni delectus officia molestiae esse sit corporis nisi consectetur, sint doloribus architecto suscipit neque sunt. Id rem, quaerat corporis ex harum blanditiis!</p>
            <h4 class="mt-3">+62 8741 2589 633</h4>
            <v-divider></v-divider>
            
           </v-col>
           <v-spacer></v-spacer>
           <v-col
             xs="12"
             sm="5"
             md="5"
           >
            <v-row wrap>
               <v-col 
                xs="4"
                sm="4"
                md="4"
                v-for="(n, i) in 3" :key="i"
               >
                  <p class="ma-0 pa-0">Judul</p>
                  <p class="ma-0 pa-0">itemitem item</p>
                  <p class="ma-0 pa-0">itemitem item</p>
                  <p class="ma-0 pa-0">itemitem item</p>
                  <p class="ma-0 pa-0">itemitem item</p>
                  <p class="ma-0 pa-0">itemitem item</p>
               </v-col>
               <v-col 
                xs="4"
                sm="4"
                md=""
               >

               </v-col>
               <v-col 
                xs="4"
                sm="4"
                md=""
               >

               </v-col>
            </v-row>
           </v-col>
         </v-row>
       </v-container>
  </v-app>
</template>

<script>
  export default {
    name: 'App',
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
      email:null,
      flightDeals: null,
      items: [
        { icon: 'mdi-trending-up', text: 'Most Popular' },
        { icon: 'mdi-youtube-subscription', text: 'Subscriptions' },
        { icon: 'mdi-history', text: 'History' },
        { icon: 'mdi-playlist-play', text: 'Playlists' },
        { icon: 'mdi-clock', text: 'Watch Later' },
      ],
      items2: [
        { picture: 28, text: 'Joseph' },
        { picture: 38, text: 'Apple' },
        { picture: 48, text: 'Xbox Ahoy' },
        { picture: 58, text: 'Nokia' },
        { picture: 78, text: 'MKBHD' },
      ],
      links: [
        {text: 'Flight', route: '/flight'},
        {text: 'Hotel', route: '/hotel'},
        {text: 'Packages', route: '/packages'},
        {text: 'My Trips', route: '/mytrips'},
        {text: 'Support', route: '/support'},
        {text: 'Sign In', route: '/signin'},
      ],
      flightOptions: [
        {text:'one way'},
        {text:'round trip'},
        {text:'multi city'}
      ],
      destinations: [
        {text:'city A'},
        {text:'city B'},
        {text:'city C'},
        {text:'city D'},
      ]
    }),
  }
</script>