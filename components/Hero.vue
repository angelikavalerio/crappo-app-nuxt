<template>
  <section id="home" class="hero">
    <div class="hero__content">
      <div class="hero__content--side hero__content--side-1">
        <div class="sale-banner">
          <div class="sale-banner--emphasize">
            <span class="emphasis-text">75% save</span>
          </div>
          <span class="sale-banner--text">For the Black Friday weekend</span>
        </div>
        <h1 class="hero__title mt-md">
          Fastest & secure platform to invest in crypto
        </h1>
        <p class="text-primary mt-md">
          Buy and sell cryptocurrencies, trusted by 10M wallets with over $30 billion in transactions.
        </p>
        <ActionButton class="mt-lg">
          Try for FREE
          <icon-wrapper class="chevron-right">
            <img src="~/assets/images/eva_chevron-right-outline.svg" alt="chevron right" class="icon chevron-right__icon">
          </icon-wrapper>
        </ActionButton>
      </div>
      <div class="hero__content--side hero__content--side-2">
        <img src="~/assets/images/hero-img.png" alt="hero img" class="hero__img">
        <img src="~/assets/images/shadow-1.png" alt="chevron right" class="hero__shadow hero__shadow--1">
        <img src="~/assets/images/shadow-2.png" alt="chevron right" class="hero__shadow hero__shadow--2">
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.hero {
  padding: 3rem 2rem 10rem 2rem;

  .text-primary {
    max-width: 43.5rem;
  }

  &__content {
    @include flex-align-center;

    &--side {
      width: 100%;

      .sale-banner {
        max-width: 34.5rem;
        width: 100%;
        padding: 4px;
        border-radius: 3.2rem;
        background: rgba(255, 255, 255, 0.10);
        @include flex-align-center;
        justify-content: space-between;

        &--emphasize {
          border-radius: 3.6rem;
          padding: 4px 1.6rem;
          background: $white;
          @include flex-align-center;

          .emphasis-text {
            color: black;
            text-transform: capitalize;
          }
        }

        &--text {
          margin-right: 1rem;
        }
      }

      .hero__title {
        font-size: 6.4rem;
        font-weight: 700;
        line-height: 7.5rem;
        max-width: 58.8rem;
      }

      .hero__img {
        width: 100%;
      }

      .hero__shadow {
        position: absolute;
      }

      .hero__shadow--1 {
        right: 15%;
        top: 0;
        margin-top: 42rem;
      }

      .hero__shadow--2 {
        right: 0;
        top: 0;
        margin-top: 48rem;
      }
    }

    &--side-1 {
      min-width: 55rem;
    }
  }
}

@media only screen and (max-width: 900px) {
  .hero {
    padding: 15rem 0;
    &__content {
      flex-direction: column;
      &--side-1 {
        min-width: 0;
      }

      &--side-2 {
        display: none;
      }

      .hero__title {
        font-size: 4.8rem;
        line-height: 5.5rem;
      }

      .sale-banner {
        justify-content: flex-start;

        &--emphasize {
          .emphasis-text {
            font-size: 1.4rem;
          }
        }

        &--text {
          font-size: 1.4rem;
          margin-left: 1rem;
        }
      }
    }

  }

}
</style>
