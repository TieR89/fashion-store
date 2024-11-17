<template>
  <div class="product-info">
    <h1 class="product-info__title">Жакет удлиненный, белый</h1>
    <p class="product-info__price">8900 RUB</p>

    <div class="product-info__options">
      <div class="product-info__sizes">
        <button
          v-for="size in sizes"
          :key="size.name"
          :class="[
            'product-info__size',
            { 'product-info__size--active': size.active },
          ]"
        >
          {{ size.label }}
          <span v-if="size.note" class="product-info__note">{{
            size.note
          }}</span>
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
      <button class="product-info__bookmark">
        <img
          src="img/ico-flag.png"
          alt="flag"
          class="header__icon-img desktop-only"
          width="24px"
        />
      </button>
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
    }
  },
}
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
    margin-top: 40px;
    top: 30px;
    font-size: 14px;
  }

  &__color {
    margin-top: 15px;
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
    height: 44px;
  }

  &__bookmark {
    width: 44px;
    height: 44px;
    border: 1px solid #080808;
    background-size: contain;
    cursor: pointer;
  }

  &__details {
    margin-top: 20px;
    font-family: Arial, sans-serif;
    width: 100%;
    max-width: 400px;
    details {
      border-bottom: 1px solid #ddd;
      margin-bottom: 10px;
    }
    summary {
      cursor: pointer;
      font-size: 16px;
      font-weight: bold;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 0;
      list-style: none;

      &::-webkit-details-marker {
        display: none; // Убираем стандартный маркер
      }

      &::after {
        content: '+';
        font-size: 20px;
        font-weight: normal;
        margin-left: auto;
        transition: transform 0.2s ease;
      }
    }

    &[open] {
      summary {
        color: #000; // Цвет при открытии

        &::after {
          content: '-';
          transform: rotate(90deg);
        }
      }
    }

    p {
      font-size: 14px;
      color: #555;
      line-height: 1.5;
      margin: 10px 0 0;
      padding-bottom: 10px;
    }
  }
}
</style>
