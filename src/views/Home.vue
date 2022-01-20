<template>
  <div class="home">
    <artist-card />
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
  background: black;
  overflow-x: hidden;
}
.bg {
  background-image: url("../assets/cloud.jpg");
  width: 100%;
  transform: rotate(180deg);
}
.page-background {
  background-size: cover;
  position: fixed;
  width: 100%;
  height: 100%;
  position: absolute;
}
.box-shadow {
  box-shadow: 0 0 28px 0 rgba(0, 0, 0, 0.8);
}
</style>
