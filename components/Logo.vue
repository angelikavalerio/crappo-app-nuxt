<template>
  <div class="logo">
    <img src="~/assets/images/Logo.svg" alt="Logo" class="logo__img">
    <span class="logo__title">Crappo</span>
  </div>
</template>

<style lang="scss">
.logo {
    display: flex;
    gap: 1.6rem;
    @include flex-align-center;

    &__title {
        text-transform: uppercase;
        font-family: Inter;
        font-size: 1.8rem;
        font-weight: 600;
        letter-spacing: 0.72px;
    }
}
</style>
