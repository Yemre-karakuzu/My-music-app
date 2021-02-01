<template>
  <div id="app">
    <header>
      <h1>My Music</h1>
    </header>
    <main>
      <section class="player">
        <h2 class="song-title">
          {{ current.title }} -
          <span>{{ current.artist }} </span>
        </h2>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      current: {},
      index: 0,
      songs: [
        {
          title: "Am I Wrong",
          artist: "Keb Mo",
          src: require("./assets/music/keb-mo-am-i-wrong.mp3"),
        },
        {
          title: "No Woman No Cry",
          artist: "Bob Marley",
          src: require("./assets/music/bob-marley-no-women-no-cry-original.mp3"),
        },
      ],
      player: new Audio(),
    };
  },
  created() {
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
    this.player.play();
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: sans-serif;
}
header {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #212121;
  color: #ffff;
}
</style>
