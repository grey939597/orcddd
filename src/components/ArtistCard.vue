<template>
  <div class="artist__container">
    <video
      src="../assets/sky.mp4"
      class="album-cover"
      @click.stop="play"
      autoplay
      playsinline
      loop
      muted
      style="transform: rotate(180deg)"
    />
    <ul class="links">
      <template v-for="(link, index) in links">
        <li :key="index">
          <a :href="link.href">{{ link.name }}</a>
        </li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ArticstCard",
  data() {
    return {
      links: [
        {
          name: "yOUtUbE",
          url: "https://youtube.com",
        },
        {
          name: "iNSTaGRaM",
          url: "https://music.apple.com",
        },
        {
          name: "pHotO",
          url: "https://melon.com",
        },
        {
          name: "MuSic",
          url: "https://www.spotify.com",
        },
      ],
      m1: null,
      m2: null,
      m3: null,
      m4: null,
      m5: null,
      show: false,
      current: "",
      currentEl: null,
    };
  },
  computed: {
    duration1() {
      return this.m1?.duration || "0:00";
    },
    duration2() {
      return this.m2?.duration || "0:00";
    },
    duration3() {
      return this.m3?.duration || "0:00";
    },
    duration4() {
      return this.m4?.duration || "0:00";
    },
    duration5() {
      return this.m5?.duration || "0:00";
    },
  },
  methods: {
    play1() {
      this.pause();
      this.current = "m1";
      this.currentEl = this.m1;
      this.play();
    },
    play2() {
      this.pause();
      this.current = "m2";
      this.currentEl = this.m2;
      this.play();
    },
    play3() {
      this.pause();
      this.current = "m3";
      this.currentEl = this.m3;
      this.play();
    },
    play4() {
      this.pause();
      this.current = "m4";
      this.currentEl = this.m4;
      this.play();
    },
    play5() {
      this.pause();
      this.current = "m5";
      this.currentEl = this.m5;
      this.play();
    },
    play() {
      // if (this.currentEl) {
      //   this.currentEl.play();
      // } else {
      this.m5.play();
      // }
    },
    pause() {
      this.m1.pause();
      this.m2.pause();
      this.m3.pause();
      this.m4.pause();
      this.m5.pause();
    },
    onClick() {
      this.show = true;
      this.pause();
    },
  },
  mounted() {
    this.m1 = new Audio("/audio/November.mp3");
    this.m2 = new Audio();
    this.m2.src = "/audio/RoseRose.mp3";
    this.m3 = new Audio();
    this.m3.src = "/audio/LoveAmbulance.mp3";
    this.m4 = new Audio();
    this.m4.src = "/audio/SingIt.mp3";
    this.m5 = new Audio();
    this.m5.src = "/audio/HumanLikeLoveLikeHuman.mp3";
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Outfit:wght@100;200;300;400;500;600;700;800;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Shadows+Into+Light&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");
* {
  /* font-family: "Outfit", sans-serif; */
  /* font-family: "Cinzel", serif; */
  /* font-family: "Shadows Into Light", cursive; */
  font-family: "Press Start 2P", cursive;
  font-weight: 400;
}
.artist__container {
  width: 100%;
  background-color: transparent;
  position: relative;
  z-index: 10;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  .album-cover {
    width: 100%;
    height: 180vw;
    object-fit: cover;
    margin: 0;
  }
  .toggle-btn {
    position: absolute;
    top: 8px;
    left: 8px;
    padding: 6px 16px;
    border-radius: 4px;
    font-size: 12px;
    color: #fff;
    background: #2e2e2e;
    z-index: 11;
    cursor: pointer;
  }
  .playlist {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.25s ease-in-out;
    &.show {
      max-height: 300px !important;
      overflow: auto !important;
    }
    li {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 16px 24px;
      background: black;
      color: #fff;
      font-size: 16px;
      cursor: pointer;
      &:hover {
        color: #dadada;
      }
      &.active {
        color: #3498db;
      }
      &:not(:last-child) {
        border-bottom: 1px solid rgb(219, 219, 219);
      }
      .music__duration {
        font-size: 12px;
      }
    }
  }
  .description {
    background-color: #2e2e2e;
    color: #fff;
    padding: 16px;
    margin: 0;
    line-height: 1.6;
    p {
      font-size: 18px;
    }
    span {
      font-size: 12px;
    }
  }
  .links {
    background-image: url("../assets/galaga2.gif");
    background-size: cover;
    background-position-y: bottom;
    height: 50vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
    li {
      /* &:not(:last-child) {
        border-bottom: 1px solid rgb(219, 219, 219);
      } */
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      a {
        all: unset;
        padding: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        font-size: 18px;
        cursor: pointer;
        color: yellow;
        &:hover {
          color: #fff;
          background-color: #9588b8;
        }
      }
    }
  }
}
</style>
