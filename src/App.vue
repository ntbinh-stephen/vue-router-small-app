<template>
  <div id="app">
    <TheNavigation />
    <transition name="moveUp">
      <router-view :key="$route.path" />
    </transition>
  </div>
</template>
<script>
import TheNavigation from "@/components/TheNavigation";
export default {
  components: {
    TheNavigation,
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
/* .slide-enter-active, .slide-leave-active {
  transition: opacity: 1s, transform: 1s;
}
.slide-enter, .slide-leave-to {
  opacity: 0;
  transform: translateX(-30%);
} */
.moveUp-enter-active {
  animation: fadeIn 1s ease-in;
}
@keyframes fadeIn {
  0%{
    opacity: 0;
  }
  50%{
    opacity: 0.5;
  }
  100%{
    opacity: 1;
  }
}
.moveUp-leave-active {
  animation: moveUp 0.3s ease-in;
}
</style>
