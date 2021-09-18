<template>
  <div id="twitch-embed" class="w-full" />
  <button id="play">Play</button>
  <button id="pause">Pause</button>
  <button id="precedent">Precedent</button>
  <button id="skip">Skip</button>
  <button id="volumeUp">VolumUp</button>
  <button id="volumeDown">VolumDown</button>
  <button id="mute">
    <span v-if="muted">UnMute</span>
    <span v-else>Mute</span>
  </button>
</template>

<script>
export default {
  props: {
    video: {
      type: String,
      default: "1148356867",
    },
    width: {
      type: String,
      default: "100%",
    },
    height: {
      type: String,
      default: "400",
    },
    mute: {
      type: Boolean,
      default: true,
    },
    autoplay: {
      type: Boolean,
      default: true,
    },
    controls: {
      type: Boolean,
      default: false,
    },
    allowfullscreen: {
      type: Boolean,
      default: true,
    },
  },
  mounted() {
    this.createScript();
    setTimeout(() => {
      this.showVideo();
    }, 200);
  },
  data() {
    return {
      muted: false,
    };
  },
  methods: {
    createScript() {
      var tag = document.createElement("script");
      tag.src = "https://player.twitch.tv/js/embed/v1.js";
      var firstScriptTag = document.getElementsByTagName("script")[0];
      firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);
    },
    showVideo() {
      const options = {
        width: this.width,
        height: 480,
        video: this.video,
        // Only needed if this page is going to be embedded on other websites
        parent: ["pi"],
        muted: this.mute,
        autoplay: this.autoplay,
        controls: this.controls,
        allowfullscreen: this.allowfullscreen,
      };
      const player = new Twitch.Embed("twitch-embed", options);

      document.getElementById("play").addEventListener("click", (e) => {
        player.disableCaptions();
        player.play();
      });
      document.getElementById("pause").addEventListener("click", (e) => {
        player.pause();
      });
      document.getElementById("skip").addEventListener("click", (e) => {
        const currentTime = player.getCurrentTime() + 60;
        player.seek(currentTime);
      });
      document.getElementById("precedent").addEventListener("click", (e) => {
        const currentTime = player.getCurrentTime() - 60;
        player.seek(currentTime);
      });
      document.getElementById("volumeUp").addEventListener("click", (e) => {
        const volume = player.getVolume() + 0.1;
        player.setVolume(volume);
      });
      document.getElementById("volumeDown").addEventListener("click", (e) => {
        const volume = player.getVolume() - 0.1;
        player.setVolume(volume);
      });
      document.getElementById("mute").addEventListener("click", (e) => {
        if (this.muted === false) {
          this.muted = true;
          player.setMuted(true);
        } else {
          this.muted = false;
          player.setMuted(false);
        }
      });
    },
  },
};
</script>