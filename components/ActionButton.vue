<template>
  <button class="button">
    <slot />
  </button>
</template>

<style lang="scss">
  .button {
    background: $color-accent;
    border: 1px solid $color-accent;
    color: $white;
    font-weight: 500;
    border-radius: 3.2rem;
    padding: 1.4rem 3.2rem;
    cursor: pointer;
    @include flex-align-center;
    gap: 2.4rem;
    justify-content: center;

    &:hover {
      transform: translateY(-2px);
    }

    &:active {
      transform: translateY(0);
    }
  }
</style>
