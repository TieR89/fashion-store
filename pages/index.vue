<template>
  <div class="index-page">
    <!-- Карточка продукта -->
    <Product />

    <!-- Секция с похожими товарами -->
    <RelatedProducts />
  </div>
</template>

<script>
import Product from '~/components/Product'
import RelatedProducts from '~/components/RelatedProducts'

export default {
  components: {
    Product,
    RelatedProducts,
  },
}
</script>

<style scoped lang="scss">
.index-page {
  max-width: 1440px;
  margin: 0 auto;
  padding: 20px;
}
.product {
  width: 1040px;
  margin: 0 auto;
}
</style>
