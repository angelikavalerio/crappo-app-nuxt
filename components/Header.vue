<script setup>
import { store } from '../stores.js'

function toggleNav() {
  store.isNavOpen = !store.isNavOpen
}
</script>

<template>
  <div class="header">
    <div class="header__content">
      <Logo />
      <Navigation class="navDesktop" />
      <div class="veggie-icon" :class="{ open: store.isNavOpen }" @click="toggleNav" />
      <div class="backdrop" :class="{ open: store.isNavOpen }">
        <Navigation :show-extend="false" />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.header {
    position: -webkit-sticky;
    position: sticky;
    width: 100%;
    top: 0;
    left: 0;
    padding: 4rem 2rem;
    z-index: 99999;
    background-color: $primary-color;

    &__content {
      display: flex;
      justify-content: space-between;
      max-width: 1200px;
      margin: 0 auto;
    }
}

.veggie-icon {
  display: none;
  position: relative;
  height: 6rem;
  width: 6rem;
  border-radius: 3rem;
  cursor: pointer;
  z-index: 9;

  &::before, &::after {
    content: "";
    height: 4px;
    width: 4rem;
    background-color: $white;
    position: absolute;
    transition: all .5s;
    text-align: center;
    left: 50%;
    transform: translateX(-50%);
  }

  &::before {
    top: 2.35rem

  }

  &::after {
    bottom: 2.3rem;
  }
}

.veggie-icon.open {
  background-color: $color-accent !important;
  &::before, &::after {
    left: 60%;
    transform-origin: left;
  }
  &::before {
    transform: translateX(-50%) rotate(45deg);
    top: 1.4rem;

  }
  &::after {
    transform:translateX(-50%) rotate(-45deg);
    bottom: 1.4rem;
  }

}

.backdrop {
  display: none;
}

@media only screen and (max-width: 900px) {
  .header {
    padding: 2rem;
  }

  .navDesktop {
    display: none !important;
  }

  .veggie-icon {
    display: inline-block;
  }

  .backdrop.open{
    width: 100%;
    height: 100vh;
    border-radius: 0;
    opacity: 1;
    position: fixed;
  }

  .backdrop  {
    position: absolute;
    top: 0;
    left: 0;
    width: 6rem;
    height: 6rem;
    border-radius: 3rem;
    background-color: $color-accent;
    z-index: 1;
    transition: all .5s;
    opacity: 0;
    @include flex-align-center;
    justify-content: center;

    .navigation__list {
      flex-direction: column;
      align-items: center;

      &--item {
        background-color: transparent;

        &:hover {
          transform: scale(1.1) rotate(8deg);
          box-shadow: none;
        }
      }
    }
  }
}
</style>
