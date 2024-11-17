<template>
  <div>
    <header class="header">
      <div class="header__left">
        <button class="header__icon">
          <img src="img/ico-man.png" alt="man" class="header__icon-img" />
        </button>
        <button class="header__icon">
          <img src="img/ico-search.png" alt="Search" class="header__icon-img" />
        </button>
      </div>

      <div class="header__logo">
        <img src="img/logo.png" alt="Logo" class="header__logo-img" />
      </div>

      <div class="header__right">
        <button class="header__icon">
          <img
            src="img/ico-search.png"
            alt="Search"
            class="header__icon-img desktop-only"
          />
        </button>
        <button class="header__icon">
          <img
            src="img/ico-flag.png"
            alt="flag"
            class="header__icon-img desktop-only"
          />
        </button>
        <button class="header__icon">
          <img
            src="img/ico-man.png"
            alt="man"
            class="header__icon-img desktop-only"
          />
        </button>
        <button class="header__icon">
          <img src="img/ico-bag.png" alt="bag" class="header__icon-img" />
        </button>
      </div>
    </header>

    <main>
      <Nuxt />
    </main>
  </div>
</template>

<style scoped lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  border-bottom: 1px solid #eee;
  position: relative;

  &__logo-img {
    height: 24px;
  }

  &__left {
    display: none;
  }

  &__right {
    display: flex;
    gap: 15px;
  }

  &__icon {
    font-size: 20px;
    margin: 10px;
    background: none;
    border: none;
    cursor: pointer;
  }

  &__icon-img {
    width: 20px;
    height: 20px;
  }

  @media (min-width: 376px) {
    &__left {
      display: none;
    }

    &__logo-img {
      position: absolute;
      top: 30px;
      left: 50%;
      transform: translateX(-50%);
    }
  }

  @media (max-width: 375px) {
    &__left {
      display: flex;
      gap: 15px;
      order: 1;
    }

    &__logo {
      order: 2;
    }

    &__right {
      order: 3;

      .desktop-only {
        display: none;
      }
    }

    &__logo-img {
      display: block;
      margin: 0 auto;
    }
  }
}
</style>
