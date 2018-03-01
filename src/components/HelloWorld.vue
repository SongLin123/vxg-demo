<template>
  <div>
    	<div 
    id="vxg_media_player1" 
    width="640"
    height="480"
    url="rtsp://admin:liguowei123456@172.16.12.65:554"
    nmf-src="/static/pnacl/Release/media_player.nmf"
    nmf-path="media_player.nmf"
    useragent-prefix="MMP/3.0"
    latency="10000"
    volume="0"
    avsync
    mute
    aspect-ratio
    aspect-ratio-mode="1"
    auto-reconnect
    connection-timeout="5000"
    connection-udp="0"
    custom-digital-zoom></div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  created() {
    this.$nextTick(() => {
      vxgplayer("vxg_media_player1").ready(() => {
        vxgplayer("vxg_media_player1").play();
        console.log("player LOADED: versionPLG=" + vxgplayer('vxg_media_player1').versionPLG()+" versionAPP="+vxgplayer('vxg_media_player1').versionAPP());
      });
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
