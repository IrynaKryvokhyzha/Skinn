<template>
  <MainMasterPage>
    <div class="blog">
      <h1>This is an blog page</h1>
    </div>
  </MainMasterPage>
</template>
<script setup>
import MainMasterPage from "@/masterpages/MainMasterPage.vue";
</script>
<style>
@media (min-width: 1024px) {
  .blog {
    min-height: 100vh;

    align-items: center;
  }
}
</style>
