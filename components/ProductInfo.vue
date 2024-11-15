<template>
  <div class="product-info">
    <h1 class="product-info__title">Жакет удлиненный, белый</h1>
    <p class="product-info__price">8900 RUB</p>

    <div class="product-info__options">
      <div class="product-info__sizes">
        <button
          v-for="size in sizes"
          :key="size.name"
          :class="['product-info__size', { 'product-info__size--active': size.active }]"
        >
          {{ size.label }}
          <span v-if="size.note" class="product-info__note">{{ size.note }}</span>
        </button>
      </div>
      <p class="product-info__color-label">Цвет: белый</p>
      <div class="product-info__colors">
        <span
          v-for="color in colors"
          :key="color"
          :style="{ backgroundColor: color }"
          class="product-info__color"
        ></span>
      </div>
    </div>

    <div class="product-info__actions">
      <button class="product-info__button">Добавить в корзину</button>
      <button class="product-info__bookmark"></button>
    </div>

    <div class="product-info__details">
      <details>
        <summary>Описание</summary>
        <p>Описание товара...</p>
      </details>
      <details>
        <summary>Состав и уход</summary>
        <p>Информация о составе и уходе...</p>
      </details>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sizes: [
        { label: 'XS', active: false, note: 'мало' },
        { label: 'S', active: true, note: null },
        { label: 'M', active: false, note: 'подписка' },
      ],
      colors: ['#FFFFFF', '#000000', '#D2B48C'],
    };
  },
};
</script>

<style lang="scss" scoped>
.product-info {
  &__title {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 10px;
  }

  &__price {
    font-size: 20px;
    margin-bottom: 20px;
  }

  &__sizes,
  &__colors {
    display: flex;
    gap: 8px;
    margin-bottom: 10px;
  }

  &__size {
    padding: 10px;
    background-color: #f3f3f3;
    border: 1px solid #080808;
    width: 65px;
    height: 31px;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: center;

    &--active {
      background-color: #000;
      color: #fff;
    }
  }

  &__note {
    font-size: 12px;
    color: #808080;
    margin: 10px;
  }

  &__color-label {
    margin: 30px;
    top: 30px;
    font-size: 14px;
  }

  &__color {
    width: 28px;
    height: 28px;
    border: 1px solid #080808;
  }

  &__actions {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 20px;
  }

  &__button {
    padding: 10px;
    background-color: #000;
    color: #fff;
    border: none;
    cursor: pointer;
    width: 100%;
  }

  &__bookmark {
    width: 28px;
    height: 28px;
    background: url('/path/to/bookmark-icon.svg') no-repeat center;
    background-size: contain;
    border: none;
    cursor: pointer;
  }

  &__details {
    margin-top: 20px;

    details {
      margin-bottom: 10px;
    }
  }
}
</style>
