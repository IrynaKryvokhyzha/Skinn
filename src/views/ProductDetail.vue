<template>
  <section class="product-detail">
    <div v-if="product" class="product-detail__container">
      <div class="product-detail__image-ibg">
        <img :src="product.image" :alt="product.name" />
      </div>
      <div class="product-detail__content content">
        <h1 class="content__name">{{ product.name }}</h1>
        <p class="content__category">{{ product.category }}</p>
        <p class="content__price">{{ product.price }}</p>
        <p class="content__description paragraph">{{ product.description }}</p>
        <div class="product-detail__actions">
          <a href="#" @click="goToShop">To products</a>
          <button class="button">Add to cart</button>
        </div>
      </div>
    </div>
    <p v-else>Loading...</p>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { useRoute } from "vue-router";
import { useRouter } from "vue-router";

const router = useRouter();
const route = useRoute();
const product = ref(null);

function goToShop() {
  router.push("/shop-all");
}

onMounted(async () => {
  try {
    const response = await fetch("/data/products.json");
    const products = await response.json();
    product.value = products.find((p) => p.id === Number(route.params.id));
  } catch (error) {
    console.error("Failed to fetch product details:", error);
  }
});
</script>

<style lang="scss" scoped>
@use "../assets/styles/common-styles/container.scss" as *;
@use "../assets/styles/common-styles/common.scss" as *;

.product-detail {
  // .product-detail__container
  &__container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
  }

  // .product-detail__image
  &__image-ibg {
    padding: 20%;
  }

  // .product-detail__content

  &__content {
  }

  &__actions {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    gap: 20px;
  }
}
.content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 20px;
  // .content__name

  &__name {
    font-size: 2rem;
    color: $secondaryColor;
    font-weight: 500;
  }

  // .content__category

  &__category {
  }

  // .content__price

  &__price {
  }

  // .content__description

  &__description {
    text-align: start;
  }
}
.button {
  width: fit-content;
  border-radius: 5px;
}
a {
  text-decoration: underline;
  transition: color 0.3s ease;
  @media (any-hover: hover) {
    &:hover {
      color: $secondaryColor;
    }
  }
}
</style>
