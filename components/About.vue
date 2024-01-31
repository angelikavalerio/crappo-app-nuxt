<script setup>
import { reactive } from 'vue'

const aboutGroup = reactive([
  {
    src: '/icons/bar-chart.svg',
    iconName: 'bar chart',
    heading: '$30B',
    subheading: 'Digital Currency Exchanged',
  },
  {
    src: '/icons/person.svg',
    iconName: 'person',
    heading: '10M+',
    subheading: 'Trusted Wallets Investor',
  },
  {
    src: '/icons/earth.svg',
    iconName: 'earth',
    heading: '195',
    subheading: 'Countries Supported',
  },
])
</script>

<template>
  <section id="about" class="about">
    <div class="grid">
      <div class="grid__row">
        <div v-for="(item, i) in aboutGroup" :key="i" class="grid__col grid__col--about">
          <icon-wrapper class="about-icon">
            <img :src="`${item.src}`" alt="bar chart" class="icon">
          </icon-wrapper>
          <div class="about-details">
            <h4 class="heading-primary">
              {{ item.heading }}
            </h4>
            <p class="about-details__subheading">
              {{ item.subheading }}
            </p>
          </div>
        </div>
      </div>
      <div class="grid__row align-center py-100">
        <div class="grid__col image">
          <img src="~/assets/images/about-img.png" alt="about img" class="grid__img">
          <img src="~/assets/images/shadow-3.png" alt="about img" class="shadow shadow--1">
        </div>
        <div class="grid__col flex-col">
          <h1 class="heading-primary">
            Why you should choose CRAPPO
          </h1>
          <p class="text-primary mt-md">
            Experience the next generation cryptocurrency platform. No financial borders, extra fees, and fake reviews.
          </p>
          <ActionButton class="mt-lg">
            Learn More
          </ActionButton>
        </div>
      </div>
      <div class="grid__row mt-100">
        <h1 class="heading-primary text-center">
          Check how much you can earn
        </h1>
      </div>
      <div class="grid__row">
        <p class="text-primary mt-md text-center text-primary--2">
          Let’s check your hash rate to see how much you will earn today, Exercitation veniam consequat sunt nostrud amet.
        </p>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.about {
  padding-top: 14rem;
  padding-bottom: 23rem;

  .grid__col--about {
    gap: 2.4rem;
  }

  .about-icon {
    width: 8rem !important;
    height: 8rem;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 4rem;
  }

  .about-details__subheading {
    letter-spacing: 0.16px;
    line-height: 2rem;
  }

  .heading-primary {
    max-width: 60rem;
  }

  .text-primary {
    max-width: 40.8rem;
  }

  .text-primary--2 {
    max-width: 44.8rem;
  }

  .shadow--1 {
    top: 0;
    left: 0;
    margin-top: 125rem;
  }
}

@media only screen and (max-width: 1200px) {
  .about {
    .heading-primary, .text-primary  {
      max-width: 100%;
      text-align: center;
    }

    &-details__subheading {
      text-align: center;
      margin-top: 1rem;
    }
    .grid__row {
      gap: 2rem;

      .grid__col {
        align-items: center;

      }
    }
    .grid__col--about {
      gap: 1rem;
      flex-direction: column;
      align-items: center;
    }
  }

}

@media only screen and (max-width: 900px) {
  .about {
    .heading-primary, .text-primary  {
      max-width: 100%;
      text-align: center;
    }

    .shadow {
      display: none;
    }

  }
}

@media only screen and (max-width: 700px) {
  .about {
    .grid__row {
      flex-direction: column;
      gap: 5rem;

      .grid__col {
        align-items: center;
      }
    }
    .grid__col--about {
      gap: 1rem;
      flex-direction: column;
      align-items: center;
    }
  }
}
</style>
