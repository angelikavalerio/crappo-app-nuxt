<template>
  <section id="features" class="feature py-100">
    <section class="feature__content">
      <img src="~/assets/images/shadow-4.png" alt="shadow" class="shadow shadow--2">
      <img src="~/assets/images/shadow-5.png" alt="shadow" class="shadow shadow--3">
      <h1 class="heading-primary text-center mb-100">
        Market sentiments, portfolio, and run the infrastructure of your choice
      </h1>
      <div class="grid">
        <div class="grid__row">
          <div class="grid__col">
            <h5 class="heading-tertiary">
              Invest Smart
            </h5>
            <p class="text-primary mt-md">
              Get full statistic information about the behaviour of buyers and sellers will help you to make the decision.
            </p>
            <ActionButton class="mt-lg">
              Learn more
            </ActionButton>
          </div>
          <div class="grid__col">
            <img src="~/assets/images/chart.png" alt="feature 1" class="feature__img">
          </div>
        </div>
        <div class="grid__row mt-120 grid__row--2">
          <div class="grid__col grid__col--feature-2">
            <img src="~/assets/images/statistic.png" alt="feature 2" class="feature__img feature__img--2">
          </div>
          <div class="grid__col">
            <h5 class="heading-tertiary">
              Detailed Statistics
            </h5>
            <p class="text-primary mt-md">
              View all mining related information in realtime, at any point at any location and decide which polls you want to mine in.
            </p>
            <ActionButton class="mt-lg">
              Learn more
            </ActionButton>
          </div>
        </div>
        <div class="grid__row mt-100">
          <div class="grid__col">
            <h5 class="heading-tertiary">
              Grow your profit and track your investments
            </h5>
            <p class="text-primary mt-md">
              Use advanced analytical tools. Clear TradingView charts let you track current and historical profit investments.
            </p>
            <ActionButton class="mt-lg">
              Learn more
            </ActionButton>
          </div>
          <div class="grid__col grid__col--feature-3">
            <img src="~/assets/images/table.png" alt="feature 1" class="feature__img feature__img--3">
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<style lang="scss">
.feature {
  background-color: $secondary-color;
  max-width: 100%;
  position: relative;

  .shadow--2 {
      top: 0;
  }

  .shadow--3 {
      bottom: 0;
      right: 0;
  }

  .heading-primary {
      max-width: 75.8rem;
      margin: 0 auto;
  }

  .grid__row {
    align-items: center;
    gap: 0;

    .heading-tertiary {
        max-width: 45rem;
    }

    .grid__col {
      flex-direction: column;

      .feature__img {
          width: 100%;
          max-width: 58rem;
          z-index: 4;
      }

      .feature__img--2 {
          margin-left: -20rem;
          max-width: 71rem;
      }

      .feature__img--3 {
          max-width: 68rem;
      }

      .text-primary {
          max-width: 40.5rem;
      }
    }

    .grid__col--feature-2, .grid__col--feature-3 {
        width: 150%;
    }
  }

}

@media only screen and (max-width: 1200px) {
  .feature {
    .grid__row {
      .grid__col {
        .feature__img--2 {
          margin-left: 0;
          max-width: 80%;
        }
      }
    }
  }
}

@media only screen and (max-width: 900px) {
  .feature {

    .shadow {
      display: none;
    }

    .grid__row {
      flex-direction: column-reverse;
      gap: 4rem;

      .grid__col {
        align-items: center;

        .feature__img {
          width: 100%;
          max-width: 58rem;
          z-index: 4;
        }
        .feature__img--2 {
          max-width: 100%;
        }

        .feature__img--3 {
            max-width: 100%
        }
      }

      .heading-tertiary {
        max-width: 100%;
        text-align: center;
      }

      .text-primary {
        text-align: center;
      }
      .grid__col--feature-2, .grid__col--feature-3 {
        width: 100%;
      }

    }
    .grid__row--2 {
      flex-direction: column !important;
    }

  }
}
</style>
