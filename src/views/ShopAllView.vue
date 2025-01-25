<template>
  <MainMasterPage>
    <div class="about">
      <h1>This is an about page</h1>
    </div>
  </MainMasterPage>
</template>
<script setup>
import MainMasterPage from "@/masterpages/MainMasterPage.vue";
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;

    align-items: center;
  }
}
</style>
