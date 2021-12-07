<template>
  <div class="home">
    <div class="bg page-background"></div>
    <artist-card class="box-shadow" />
  </div>
</template>

<script>
// @ is an alias to /src
import ArtistCard from "@/components/ArtistCard.vue";

export default {
  name: "Home",
  components: {
    ArtistCard,
  },
};
</script>

<style lang="scss" scoped>
.home {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.bg {
  background-image: url("../assets/bg-cover.jpg");
}
.page-background {
  background-size: cover;
  filter: blur(50px);
  position: fixed;
  width: 100%;
  height: 100%;
  transition: all 0.1s ease;
  opacity: 0.95;
  position: absolute;
}
.box-shadow {
  box-shadow: 0 0 28px 0 rgba(0, 0, 0, 0.8);
}
</style>
