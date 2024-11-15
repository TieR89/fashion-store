<template>
  <div class="product">
    <ProductGallery class="product__gallery" />
    <ProductInfo class="product__info" />
  </div>
</template>

<script>
import ProductGallery from './ProductGallery'
import ProductInfo from './ProductInfo'

export default {
  components: {
    ProductGallery,
    ProductInfo,
  },
}
</script>

<style lang="scss" scoped>
.product {
  display: flex;
  justify-content: space-between;
  padding: 10px;

  &__gallery {
    width: 60%;
  }

  &__info {
    width: 35%;
    display: flex;
    flex-direction: column;
  }

  @media (max-width: 768px) {
    flex-direction: column;
    align-items: center;

    &__gallery,
    &__info {
      width: 100%;
    }
  }
  @media (min-width: 375px) {
    padding: 0px;

    &__gallery {
      margin-bottom: 20px;
    }

    &__info {
      align-items: center;
    }
  }
}
</style>
