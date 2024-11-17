<template>
  <div class="product-gallery">
    <div class="product-gallery__thumbnails">
      <img
        v-for="(image, index) in images"
        :key="index"
        :src="image"
        alt="Product thumbnail"
        class="product-gallery__thumbnail"
        @click="setMainImage(image)"
      />
    </div>
    <div class="product-gallery__main">
      <img
        :src="currentImage"
        alt="Main product image"
        class="product-gallery__main-image"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: ['img/picture.png'],
      currentImage: 'img/picture.png',
    }
  },
  methods: {
    setMainImage(image) {
      this.currentImage = image
    },
  },
}
</script>

<style lang="scss" scoped>
.product-gallery {
  display: flex;
  gap: 20px;

  &__thumbnails {
    display: flex;
    flex-direction: column;
    gap: 10px;

    @media (max-width: 1060px) {
      display: none;
    }
  }

  &__thumbnail {
    width: 60px;
    height: auto;
    cursor: pointer;
  }

  &__main {
    flex: 1;
    max-width: 518px;

    @media (max-width: 768px) {
      max-width: 100%;
    }
  }

  &__main-image {
    width: 100%;
    height: 693px;
    object-fit: contain;

    @media (max-width: 768px) {
      height: auto;
      aspect-ratio: 518 / 693;
    }
  }
}
</style>
