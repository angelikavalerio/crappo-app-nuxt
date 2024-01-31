<template>
  <section class="footer">
    <div class="grid">
      <div class="grid__row">
        <div class="grid__col">
          <Logo />
        </div>
        <div class="grid__col">
          <p class="footer__title">
            Quick Links
          </p>
          <Navigation :show-extend="false" class="mt-md" />
        </div>
        <div class="grid__col">
          <p class="footer__title">
            Resources
          </p>
          <ul class="resources__list">
            <li class="resources__list--item">
              <a href="#">Download Whitepapper</a>
            </li>
            <li class="resources__list--item">
              <a href="#">Smart Token</a>
            </li>
            <li class="resources__list--item">
              <a href="#">Blockchain Explorer</a>
            </li>
            <li class="resources__list--item">
              <a href="#">Crypto API</a>
            </li>
            <li class="resources__list--item">
              <a href="#">Interest</a>
            </li>
          </ul>
        </div>
        <div class="grid__col footer__col-4">
          <h5 class="heading-tertiary">
            We accept following payment systems
          </h5>
          <div class="grid">
            <div class="grid__row payment_icons">
              <div class="grid__col">
                <icon-wrapper class="payment">
                  <img src="~/assets/images/bx_bxl-visa.svg" alt="visa" class="icon">
                </icon-wrapper>
              </div>
              <div class="grid__col">
                <icon-wrapper class="payment">
                  <img src="~/assets/images/logos_mastercard.svg" alt="mastercard" class="icon">
                </icon-wrapper>
              </div>
              <div class="grid__col">
                <icon-wrapper class="payment">
                  <img src="~/assets/images/logos_bitcoin.svg" alt="bitcoin" class="icon">
                </icon-wrapper>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="grid__row grid__row--2">
        <div class="grid__col">
          <p class="text-primary">
            ©2021 CRAPPO. All rights reserved
          </p>
        </div>
        <div class="grid__col social_icons">
          <img src="~/assets/images/facebook-f.svg" alt="facebook" class="icon">
          <img src="~/assets/images/instagram.svg" alt="instagram" class="icon">
          <img src="~/assets/images/youtube.svg" alt="youtube" class="icon">
          <img src="~/assets/images/twitter.svg" alt="twitter" class="icon">
          <img src="~/assets/images/linkedin.svg" alt="linkedin" class="icon">
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.footer {
  padding-bottom: 8rem;

  &__title {
    font-size: 2rem;
    font-style: normal;
    font-weight: 500;
    line-height: 3.8rem;
  }

  .heading-tertiary {
    width: 35.5rem;
  }

  .navigation__list {
    flex-direction: column;
  }

  .resources__list {
    display: flex;
    flex-direction: column;
    list-style: none;
    padding: 0;
    margin: 0;
    margin-top: 2.4rem;
    gap: 3.2rem;

    &--item {
      background-color: $primary-color;

      &:hover {
        @include link-hover;
      }
    }
  }

  .grid__row {
    gap: 0;

    .grid__col {
      flex-direction: column;
    }

    .payment_icons {
      gap: 2.4rem;
      margin-top: 4rem;
      flex-direction: row;

      .payment {
        width: 9.6rem;
        height: 6.4rem;
        border-radius: 8px;
        background-color: rgb(224, 224, 224, 0.05);
      }
    }

    .social_icons{
      justify-content: flex-end;
      flex-direction: row;
      gap: 3.2rem;
    }
  }

  .grid__row--2 {
    margin-top: 12rem;
  }
}

@media only screen and (max-width: 1200px) {
  .footer {
    .resources__list {
      &--item {
        max-width: 80%;

      }
    }

    .grid__row--2 {
    margin-top: 8rem;
  }
  }

}

@media only screen and (max-width: 900px) {
   .footer {
    padding-bottom: 3rem;

    .heading-tertiary {
      text-align: center;
    }

    .grid__row {
      flex-direction: column;
      gap: 3rem;

      .grid__col {
        align-items: center;

        .navigation__list {
          align-items: center;
        }

        .resources__list {
          align-items: center;

          &--item {
            max-width: 100%;
          }
        }

      }

        .payment_icons {
          flex-direction: row;
        }
    }

    .grid__row--2 {
      flex-direction: column-reverse;

      .social_icons {
          justify-content: center;
        }
    }
  }
}
</style>
