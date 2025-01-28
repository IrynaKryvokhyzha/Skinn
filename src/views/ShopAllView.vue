<template>
  <MainMasterPage>
    <ProductsComponent class="products-component" />
  </MainMasterPage>
</template>
<script setup>
import MainMasterPage from "@/masterpages/MainMasterPage.vue";
import ProductsComponent from "@/components/ProductsComponent.vue";
</script>
<style>
.products-component {
  padding-top: 100px;
}
</style>
