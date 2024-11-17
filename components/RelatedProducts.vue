<template>
  <div class="related-products">
    <h2 class="related-products__title">Похожие товары</h2>
    <div class="related-products__items">
      <div
        v-for="(product, index) in products"
        :key="index"
        class="related-products__item"
      >
        <img
          :src="product.image"
          alt="Product image"
          class="related-products__image"
        />
        <p class="related-products__name">{{ product.name }}</p>
        <p class="related-products__price">{{ product.price }} RUB</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { image: 'img/pic1.png', name: 'Платье', price: '14000' },
        { image: 'img/pic2.png', name: 'Жакет', price: '8500' },
        { image: 'img/pic3.png', name: 'Платье', price: '10500' },
        { image: 'img/pic4.png', name: 'Комбинезон', price: '9500' },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.related-products {
  width: 1360px;
  margin-top: 40px;

  &__title {
    font-size: 20px;
    margin-bottom: 20px;
  }

  &__items {
    display: flex;
    gap: 20px;
  }

  &__item {
    width: 333px;
    text-align: center;
  }

  &__image {
    display: flex;
    width: 333px;
    height: 444px;
  }

  &__name {
    font-size: 16px;
    margin-top: 5px;
  }

  &__price {
    font-size: 14px;
    color: #333;
  }
}
</style>
