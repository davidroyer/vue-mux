<template>
  <div id="app">
    <div class="container">
      <h2>New Forms - Admin Overview</h2>
      <video id="myVideo" controls></video>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  mounted() {
    // Replace with your asset's playback ID
    // var playbackId = "Xr1UdWNZHbjPWzevytd2wKgdth4R9YJe";
    var playbackId = "MM2Xkc3JHw7tf3fXQyYww92Tgcx7dGPP";

    var url = "https://stream.mux.com/" + playbackId + ".m3u8";

    // HLS.js-specific setup code
    if (window.Hls.isSupported()) {
      const Hls = window.Hls;
      var video = document.getElementById("myVideo");
      var hls = new Hls();
      hls.loadSource(url);
      hls.attachMedia(video);
    }
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  .container {
    max-width: 1200px;
    padding: 2em;
    margin-left: auto;
    margin-right: auto;

    video {
      width: 100%;
      height: auto;
    }
  }
}
</style>
