<template>
  <div id="app">
    <div class="header-text">
      {{ msg }}
    </div>
    <div class="video-responsive">
      <youtube :video-id="videoId" :player-vars="{autoplay: 1, loop: 1}"></youtube>
    </div>
    <v-footer>
      <v-spacer></v-spacer>
      <div style="font-size: 20px;">Coded by <a href="https://github.com/Adem68"
                                                style="color: orange; text-decoration: none;">Adem Furkan ÖZCAN</a>
      </div>
    </v-footer>
  </div>
</template>

<script>
import Vue from 'vue';
import VueYouTubeEmbed from 'vue-youtube-embed'

Vue.use(VueYouTubeEmbed)

export default {
  name: 'app',
  data: function () {
    return {
      videoId: '4OkiH2yD-eQ',
      msg: 'Acılara yürüyor korkmuyorum...',
    };
  }
}
</script>
<style>
#app {
  font-family: "Arial";
  text-align: center;
  color: #fff;
  margin-top: 60px;
  font-size: 35px;
}

body, html {
  background-color: #000;
  padding: 0;
  margin: 0;
  width: 100%;
  min-height: 100%;
}

.video-responsive {
  overflow: hidden;
  padding-bottom: 56.25%;
  position: relative;
  margin-top: 50px;
  margin-left: 10px;
  margin-right: 10px;
  margin-bottom: 100px;
  height: 0;
}

.video-responsive iframe {
  left: 0;
  top: 0;
  height: 100%;
  width: 100%;
  position: absolute;
}

@media screen and (min-width: 601px) {
  div.header-text {
    font-size: 35px;
  }
}

/* If the screen size is 600px wide or less, set the font-size of <div> to 30px */
@media screen and (max-width: 600px) {
  div.header-text {
    font-size: 25px;
  }
}
</style>
