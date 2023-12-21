<template>
  <div id="app">
    <h1 style="text-align: center;">My test</h1>  
    <div class="loader"></div>
    <!-- <div>
    <video-player ref="player" class="video-player" :options="playerOptions" :playsinline="true" :playsinlineClass="playInlineCls"
      @play="handlePlay" @pause="handlePause" @ended="handleEnded" @error="handleError"></video-player>
  </div> -->
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      playerOptions: {
        autoplay: false,
        muted: false,
        controls: true,
        sources: [{
          src: 'https://media.w3.org/2010/05/sintel/trailer.mp4',
          type: 'video/mp4'
        }]
      },
    playInlineCls : 'vjs-tech vjs-tech-inline'
    }
  },
  methods:{
    handlePlay() {
      console.log('play');
    },
    handlePause() {
      console.log('pause');
    },
    handleEnded() {
      console.log('ended');
    },
   handleError() {
      console.log('error');
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
/* HTML: <div class="loader"></div> */
.loader {
  width: 60px;
  height: 25px;
  border: 2px solid;
  box-sizing: border-box;
  border-radius: 50%;
  display: grid;
  animation: l2 2s infinite linear;
}
.loader:before,
.loader:after {
  content: "";
  grid-area: 1/1;
  border: inherit;
  border-radius: 50%;
  animation: inherit;
  animation-duration: 3s;
}
.loader:after {
  --s:-1;
}
@keyframes l2 {
   100% {transform:rotate(calc(var(--s,1)*1turn))}
}
</style>
