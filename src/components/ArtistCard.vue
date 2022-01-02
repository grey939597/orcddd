<template>
  <div class="artist__container">
    <div class="album-cover"></div>
    <div class="description">
      <p>Earth Sandwitch Vol.1</p>
      <span>OUT NOW on All Stores!</span>
    </div>
    <ul class="links">
      <template v-for="(link, index) in links">
        <li :key="index">
          <a :href="link.href"><img :src="link.image" /></a>
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
          image: "/img/apple.png",
          url: "https://youtube.com",
        },
        {
          name: "APPLE MUSIC",
          image: "/img/youtube.png",
          url: "https://music.apple.com",
        },
        {
          name: "SPOTIFY",
          image: "/img/spotify.png",
          url: "https://www.spotify.com",
        },
        {
          name: "SOUNDCLOUD",
          image: "/img/soundcloud.png",
          url: "https://www.spotify.com",
        },
        {
          name: "DEEZER",
          image: "/img/deezer.png",
          url: "https://melon.com",
        },
        {
          name: "TIDAL",
          image: "/img/tidal.png",
          url: "https://www.spotify.com",
        },
        {
          name: "MELON",
          image: "/img/melon.png",
          url: "https://www.spotify.com",
        },
        {
          name: "GENIE",
          image: "/img/genie.png",
          url: "https://www.spotify.com",
        },
        {
          name: "BUGS",
          image: "/img/bugs.svg",
          url: "https://www.spotify.com",
        },
        {
          name: "VIBE",
          image: "/img/vibe.svg",
          url: "https://www.spotify.com",
        },
        {
          name: "FLO",
          image: "/img/flo.png",
          url: "https://www.spotify.com",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.artist__container {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  margin-bottom: auto;
  .album-cover {
    width: 100%;
    padding-bottom: 100%;
    background: linear-gradient(
        to bottom,
        rgba(255, 255, 255, 0) 50%,
        rgba(255, 255, 255, 0.2) 60%,
        rgba(255, 255, 255, 0.4) 70%,
        rgba(255, 255, 255, 0.6) 80%,
        rgba(255, 255, 255, 0.8) 90%,
        rgba(255, 255, 255, 1) 100%
      ),
      url("/img/album-cover.jpg");
    background-size: contain;
  }
  .description {
    color: #333;
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
  /* .links {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    li {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 1rem;
      a {
        all: unset;
        cursor: pointer;
        width: 18vw;
        height: 18vw;
        max-width: 86.4px;
        max-height: 86.4px;
        border-radius: 8px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-weight: 900;
        background-color: #505050;
        color: #fff;
        font-size: 2rem;
      }
    }
  } */
  .links {
    display: flex;
    flex-direction: column-reverse;
    transform: rotate(90deg);
    height: 100vw;
    overflow-y: scroll;
    gap: 8px;
    li {
      display: flex;
      justify-content: flex-start;
      height: 40px;
      img {
        height: 100%;
        object-fit: contain;
      }
    }
  }
}
</style>
