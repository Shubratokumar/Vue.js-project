<script setup>
// import ProfileCard from "./components/ProfileCard.vue";
// import VueGraph from "./components/VueGraph.vue";
// import OrgSlider from "./components/OrgSlider.vue";
import RedirectNotice from "./components/RedirectNotice.vue";
</script>

<template>
  <!-- <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />
  </header> -->
  
  <main class="flex items-center justify-center md:h-screen">
    <!-- <ProfileCard /> -->
    <!-- <VueGraph /> -->
    <!-- <OrgSlider/> -->
    <RedirectNotice/>
  </main>
</template>

<style scoped>
main{
  background-image: url(../src/assets/bg-b2c.png);
  background-repeat: no-repeat;
  background-size: cover;
}
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
