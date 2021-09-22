<template>
    <div class="music-card">
        <app-header></app-header>


      <section class="playlist">
        <button
          v-for="music in listOfMusic"
          :key="music.src"
          @click="play(music)"
          :class="music.src === currentMusic.src ? 'music playing' : 'music'"
        >
          {{ music.title }}
        </button>

        <button class="pause" @click="pause">
        停止
        </button>

       </section>
      
      <about></about>

    </div> 
</template>

<script>
import listOfMusic from "./../music";
import AppHeader from "./../components/AppHeader.vue";
import About from "./../components/About.vue"
export default {
  name: "home",
  data: function() {
    return {
      currentMusic: {},
    //   logoSrc: require("./../assets/images/headphones.png"),
    //   prevImage: require("./../assets/images/previous.png"),
    //   playImage: require("./../assets/images/play.png"),
    //   nextImage: require("./../assets/images/next.png"),
    //   pauseImage: require("./../assets/images/pause.png"),
    //   isPlaying: false,
      listOfMusic,
      player: new Audio()
    };
  },
  components: {
    AppHeader,
    About,
  },
  methods: {
    play: function(music) {
      if (typeof music.src !== "undefined") {
        this.currentMusic = music;
        this.player.src = this.currentMusic.src;
      }
      this.player.play();
      this.player.addEventListener('timeupdate', function(){
            var buffer = 1.2;
            if(this.currentTime > this.duration - buffer){
                this.currentTime = 0;
                this.play();
            }}, false);
    //   this.isPlaying = true;
    },
    pause: function() {
        this.player.pause();
    }
  }
};
</script>


<style scoped>
@import "./../css/Home.css";
</style>