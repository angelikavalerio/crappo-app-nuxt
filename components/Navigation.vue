<script setup>
import { store } from '../stores.js'

defineProps({
  showExtend: {
    type: Boolean,
    default: true,
  },
})
</script>

<template>
  <div class="navigation">
    <ul class="navigation__list" @click="store.isNavOpen = false">
      <li class="navigation__list--item">
        <a href="#home">Home</a>
      </li>
      <li class="navigation__list--item">
        <a href="#products">Products</a>
      </li>
      <li class="navigation__list--item">
        <a href="#features">Features</a>
      </li>
      <li class="navigation__list--item">
        <a href="#about">About</a>
      </li>
      <li class="navigation__list--item">
        <a href="#contact">Contact</a>
      </li>
    </ul>
    <div v-if="showExtend" class="navigation__extend">
      <a href="#" class="login">Login</a>
      <ActionButton>
        Register
      </ActionButton>
    </div>
  </div>
</template>

<style lang="scss">
.navigation {
  @include flex-align-center;
  gap: 5.6rem;

  &__list {
    list-style: none;
    display: flex;
    gap: 3.2rem;
    padding: 0;
    margin: 0;

    &--item {
      background-color: $primary-color;

      &:hover {
        @include link-hover;
      }
    }
  }

  &__extend {
    @include flex-align-center;

    .login {
      border-right: 1px solid rgba(242, 242, 242, 0.3);
      padding-right: 2.4rem;
      margin-right: 2.4rem;
    }
  }
}
</style>
