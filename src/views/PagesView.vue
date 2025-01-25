<template>
  <MainMasterPage>
    <div class="pages">
      <h1>This is an pages page</h1>
    </div>
  </MainMasterPage>
</template>
<script setup>
import MainMasterPage from "@/masterpages/MainMasterPage.vue";
</script>
<style>
@media (min-width: 1024px) {
  .pages {
    min-height: 100vh;

    align-items: center;
  }
}
</style>
