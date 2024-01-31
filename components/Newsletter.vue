<template>
  <section id="contact" class="newsletter">
    <section class="newsletter__content">
      <img src="~/assets/images/shadow-6.png" alt="shadow" class="shadow shadow--4">
      <img src="~/assets/images/shadow-7.png" alt="shadow" class="shadow shadow--5">
      <div class="grid">
        <div class="grid__row">
          <div class="grid__col">
            <h5 class="heading-tertiary">
              Start mining now
            </h5>
            <p class="text-primary mt-sm">
              Join now with CRAPPO to get the latest news and start mining now
            </p>
          </div>
          <div class="grid__col">
            <form action="#" class="form">
              <input type="email" class="form__input" placeholder="Enter your email">
              <ActionButton class="form__btn" @click.prevent="() => {}">
                Subscribe
              </ActionButton>
            </form>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<style lang="scss">
.newsletter {
  padding: 12rem 8.8rem;
  background: linear-gradient(180deg, $secondary-color 0%, $primary-color 100%);
  max-width: 100%;

  &__content {
    color: $white;
    background-color: $color-accent;
    padding: 4.8rem;
    border-radius: 1.6rem;
    position: relative;

    .shadow--4 {
        top: 0;
        left: 0;
    }

    .shadow--5 {
      bottom: 0;
      right: 0;
    }

    .grid {
      position: relative;
      z-index: 9;

      &__row {
        align-items: center;

        .grid__col {
            flex-direction: column;

          .text-primary {
            width: 37.5rem;
          }

          .form__btn {
            background-color: $white;
            color: $primary-color;
          }

          .form__input {
            min-width: 37.5rem;
            color: $white;

            &::placeholder {
                color: $white;
                width: 120%;
            }

            &:focus {
                border-bottom: 2px solid $white;
            }

          }
        }
      }
    }
  }
}

@media only screen and (max-width: 1200px) {
  .newsletter {

      .grid__row {
        flex-direction: column;
        gap: 3rem;
      }

  }
}

@media only screen and (max-width: 900px) {
  .newsletter {
    padding: 0 0 10rem 0;

    &__content {
      max-width: 100%;
      padding: 3rem;

      .grid__row {
        .grid__col {
          width: 100%;

          .form {

            &__input {
                min-width: 0;
            }
        }
        }
      }
    }
  }
}
</style>
