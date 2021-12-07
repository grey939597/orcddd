<template>
  <div class="artist__container">
    <img
      src="../assets/album-cover.jpg"
      alt="album-cover"
      class="album-cover"
      @click.stop="pause"
    />
    <!-- <div class="toggle-btn" @click="show = !show">List</div>
    <ul class="playlist" :class="{ show: show }">
      <li @click.stop="play1" :class="{ active: current === 'm1' }">
        <span class="music__title">November</span>
        <span class="music__duration">2:11</span>
      </li>
      <li @click.stop="play2" :class="{ active: current === 'm2' }">
        <span class="music__title">Rosé Rosé</span>
        <span class="music__duration">2:41</span>
      </li>
      <li @click.stop="play3" :class="{ active: current === 'm3' }">
        <span class="music__title">Love Ambulance</span>
        <span class="music__duration">3:12</span>
      </li>
      <li @click.stop="play4" :class="{ active: current === 'm4' }">
        <span class="music__title">Sing It</span>
        <span class="music__duration">2:31</span>
      </li>
      <li @click.stop="play5" :class="{ active: current === 'm5' }">
        <span class="music__title">Human Like Love Like Human</span>
        <span class="music__duration">2:57</span>
      </li>
    </ul> -->
    <div class="description">
      <p>Earth Sandwitch Vol.1</p>
      <span>OUT NOW on All Stores!</span>
    </div>
    <ul class="links">
      <template v-for="(link, index) in links">
        <li :key="index">
          <a :href="link.href"><i class="fab fa-apple"></i></a>
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
          name: "YOUTUBE",
          url: "https://youtube.com",
        },
        {
          name: "APPLE MUSIC",
          url: "https://music.apple.com",
        },
        {
          name: "MELON",
          url: "https://melon.com",
        },
        {
          name: "SPOTIFY",
          url: "https://www.spotify.com",
        },
        {
          name: "SPOTIFY",
          url: "https://www.spotify.com",
        },
        {
          name: "SPOTIFY",
          url: "https://www.spotify.com",
        },
        {
          name: "SPOTIFY",
          url: "https://www.spotify.com",
        },
        {
          name: "SPOTIFY",
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
      if (this.currentEl) {
        this.currentEl.play();
      } else {
        this.m1.play();
      }
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
.artist__container {
  * {
    box-sizing: border-box;
  }
  background-color: transparent;
  width: 100%;
  min-height: 600px;
  position: relative;
  z-index: 10;
  display: flex;
  flex-direction: column;
  margin-bottom: auto;
  .album-cover {
    width: 100%;
    object-fit: contain;
    border-top-left-radius: inherit;
    border-top-right-radius: inherit;
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
    background: #515151;
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
      font-weight: 700;
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
        font-weight: 400;
      }
    }
  }
  .description {
    background-color: transparent;
    /* background-color: #515151; */
    /* background-image: url("../assets/space.jpg");
    background-position: center;
    background-size: cover; */
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
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    li {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 30vw;
      a {
        all: unset;
        padding: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 18px;
        font-weight: 900;
        cursor: pointer;
        color: #fff;
        font-size: 2rem;
        i {
          background-color: #515151;
          padding: 5vw 5.5vw;
          border-radius: 8px;
        }
      }
    }
  }
}
</style>
