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