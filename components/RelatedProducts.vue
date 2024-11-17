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
  width: 100%;
  margin-top: 40px;

  &__title {
    font-size: 20px;
    margin-bottom: 20px;
    text-align: center;
    margin: 10px;
  }

  &__items {
    display: grid;
    grid-template-columns: repeat(4, 1fr); // 4 элемента
    gap: 10px;

    @media (max-width: 1024px) {
      grid-template-columns: repeat(3, 1fr); // 3 элемента
    }

    @media (max-width: 768px) {
      grid-template-columns: repeat(2, 1fr); // 2 элемента
    }

    @media (max-width: 375px) {
      grid-template-columns: 1fr; // 1 элемент
    }
  }

  &__item {
    text-align: center;
  }

  &__image {
    width: 100%;
    height: auto;
    object-fit: cover;
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
