<template>
  <section class="hero">
    <div class="hero__container">
      <div class="hero__content">
        <h1 class="title">
          Discover The Beauty Within <span class="title-span">You</span>
        </h1>
        <button class="button">View Collection</button>
      </div>
      <div class="hero__image"></div>
    </div>
  </section>
</template>

<script setup></script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;

.hero {
  padding-top: 100px;
  // .hero__container

  &__container {
    display: flex;
    flex-direction: row;
    height: 100vh;
    background-image: url("../assets/images/IMAGE.png");
    background-position: 100% 0%;
  }

  // .hero__content

  &__content {
    flex: 0 1 50%;
    padding: 4rem 0 0 4rem;
    @media (max-width: 1216px) {
      padding: 7rem 0 0 4rem;
      flex: 0 1 60%;
    }
    @media (max-width: $tablet) {
      flex: 0 1 90%;
      padding: 10rem 0 0 4rem;
    }
    @media screen and (max-width: $mobile) {
      padding: 10rem 0 0 0.5rem;
    }
  }

  // .hero__image

  &__image {
  }
}
.title {
  @media (max-width: $tablet) {
    font-size: 60px;
  }
  @media screen and (max-width: $mobile) {
    font-size: 40px;
    font-weight: 600;
  }
}
.title-span {
  text-align: end;
}
.button {
}
</style>
