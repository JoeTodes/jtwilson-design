<template>
  <v-app>
    <Header />

    <v-content v-cloak>
      <transition appear name="fade">
        <router-view></router-view>
      </transition>
    </v-content>
  </v-app>
</template>

<script>
import Header from "./components/Header";

export default {
  name: "App",
  components: {
    Header
  },
  data: () => ({
    //
  })
};
</script>

<style>
.fade-enter-active {
  transition: all 0.5s;
  transition-delay: 0.5s;
}

.fade-leave-active {
  transition: all 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(-64px);
}
</style>

