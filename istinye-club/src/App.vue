<template>
  <v-app>
    <v-app-bar
        color="#a51c30"
        dark
        fixed
        elevation="0"
    >
      <v-toolbar-title id="h1" style="margin-bottom: 0; padding: 10px 0;">İstinye Üniversitesi Öğrenci Kulüpleri</v-toolbar-title>
    </v-app-bar>
    <v-spacer class="ma-5"></v-spacer>
    <v-container fluid grid-list-xs v-if="!isMobile" style="background-color:#000" class="mt-5">
      <v-layout row wrap>
        <v-flex v-for="club in clubs" :key="club.id" xs4>
          <club-card :name="club.name" :img-url="club.imgUrl" :twitter="club.twitter" :instagram="club.instagram"
                     style="background-color: #323437; min-width:400px;max-width:450px;"/>
        </v-flex>
      </v-layout>
      <v-row
          style="background-color:#a51c30"
          align="center"
          justify="center"
      >
        <v-img
            class="ma-5"
            max-width="400px"
            max-height="100px"
            src="https://istinye.club/wp-content/uploads/2020/02/isu_logow-300x67.png"
        />
        <v-img
            max-width="150px"
            max-height="125px"
            src="https://istinye.club/wp-content/uploads/2020/02/pipe-2-150x150.png"
        />
        <v-img
            class="ma-5"
            max-width="250px"
            max-height="150px"
            src="https://istinye.club/wp-content/uploads/2020/02/mai_logo.png"
        />
      </v-row>
    </v-container>
    <v-container fluid grid-list-sm v-if="isMobile" style="background-color:#000">
      <v-layout
          column
          wrap
          align-center
          justify-center
      >
        <v-flex v-for="club in clubs" :key="club.id" xs4>
          <club-card :name="club.name" :img-url="club.imgUrl" :twitter="club.twitter" :instagram="club.instagram"
                     style="background-color: #323437; min-width:400px;max-width:400px;"/>
        </v-flex>
      </v-layout>
      <v-row
          style="background-color:#a51c30"
          align="center"
          justify="center">
        <v-img
            class="ma-5"
            max-width="400px"
            max-height="100px"
            src="https://istinye.club/wp-content/uploads/2020/02/isu_logow-300x67.png"
        />
      </v-row>
    </v-container>
    <v-footer padless style="background-color:#323437; margin-top: 0px">
      <v-col
          class="text-center"
          cols="12"
          style="color: white"
      >
        {{ new Date().getFullYear() }} — <strong>istinye.club</strong>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
import ClubCard from "@/components/ClubCard";
import clubs from "@/assets/clubs.json";

export default {

  name: 'App',
  beforeDestroy() {
    if (typeof window !== 'undefined') {
      window.removeEventListener('resize', this.onResize, {passive: true})
    }
  },

  mounted() {
    this.onResize()
    window.addEventListener('resize', this.onResize, {passive: true})
  },

  methods: {
    onResize() {
      this.isMobile = window.innerWidth < 1200
    },
  },
  components: {ClubCard},

  data: () => ({
    isMobile: false,
    clubs: clubs
  }),
};
</script>
<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat');

html, body {
  font-family: 'Montserrat', sans-serif;
}

#app {
  font-family: 'Montserrat', sans-serif;
}

#h1 {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
}

</style>
