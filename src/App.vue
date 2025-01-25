<template>
  <transition name="fade-page" mode="out-in">
    <router-view />
  </transition>
</template>

<style lang="scss">
@use "./assets/styles/common-styles/container.scss" as *;

nav {
  a {
    &.router-link-exact-active {
      color: $secondaryColor;
      text-decoration: underline;
    }
  }
}
.fade-page-enter-active,
.fade-page-leave-active {
  transition: opacity 0.5s;
}
.fade-page-enter-from,
.fade-page-leave-to {
  opacity: 0;
}
</style>
