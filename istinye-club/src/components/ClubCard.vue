<template>
  <v-card
      align="center"
      class="ma-5"
  >

    <v-avatar
        class="mt-5"
        rounded
        size="150"
    >
      <v-img
          lazy-src="https://istinye.club/wp-content/uploads/2020/02/isu-def-150x150.png"
          height="150"
          v-bind:src="imgUrl"
      ></v-img>
    </v-avatar>
    <v-card-title
        class="justify-center"
        style="color: white"
    >{{ name }}
    </v-card-title>

    <v-card-actions
        class="justify-center">
      <v-btn
          v-bind:href="'https://www.instagram.com/' + instagram"
          target="_blank"
          v-if="instagram !== null"
          color="orange"
          text
      >
        <v-icon
            dark
            right
            class="mr-2"
        >
          mdi-instagram
        </v-icon>
        Instagram
      </v-btn>
      <v-btn
          v-bind:href="'https://www.twitter.com/' + twitter"
          target="_blank"
          v-if="twitter !== null"
          color="blue"
          text
      >
        <v-icon
            dark
            right
            class="mr-2"
        >
          mdi-twitter
        </v-icon>
        Twitter

      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "ClubCard.vue",
  props: [
    'name',
    'imgUrl',
    'instagram',
    'twitter'
  ]
}
</script>

<style scoped>

</style>