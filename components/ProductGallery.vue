<template>
  <div class="product-gallery">
    <div class="product-gallery__thumbnails">
      <img
        v-for="(image, index) in images"
        :key="index"
        :src="image"
        alt="Product thumbnail"
        class="product-gallery__thumbnail"
        width="518px"
        height="693px"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: ['/img/picture.png'],
    }
  },
}
</script>

<style lang="scss" scoped>
.product-gallery {
  display: flex;
  &__product-gallery__thumbnails {
    width: 518px;
    height: 693px;
  }

  &__thumbnails {
    display: flex;
    flex-direction: column;
    margin-right: 20px;

    &__thumbnail {
      width: 60px;
      height: auto;
      margin-bottom: 10px;
      cursor: pointer;
    }
  }

  &__main-image {
    width: 518px;
    object-fit: cover;
  }
}
</style>
