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
  align-items: center;
  background-color: #fff;
}
</style>
