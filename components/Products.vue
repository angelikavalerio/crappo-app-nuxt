<script setup>
const selectedProduct = ref(0)

function toggleSelection(index) {
  selectedProduct.value = index
}

const products = reactive([
  {
    icon: 'icons/bitcoin.png',
    name: 'Bitcoin',
    short: 'BTC',
    desc: 'Digital currency in which a record of transactions is maintained.',
  },
  {
    icon: 'icons/etherium.png',
    name: 'Etherium',
    short: 'ETH',
    desc: 'Blockchain technology to create and run decentralized digital applications.',
  },
  {
    icon: 'icons/litecoin.png',
    name: 'Litecoin',
    short: 'LTC',
    desc: 'Cryptocurrency that enables instant payments to anyone in the world.',
  },
])
</script>

<template>
  <section id="products" class="products__container">
    <section class="products">
      <div class="calculator">
        <form action="#" class="form pb-xl">
          <input type="text" class="form__input form__input--1" placeholder="Enter your hash rate">
          <select id="cars" name="cars" class="form__input form__input--2">
            <option>
              TH/s
            </option>
            <option>
              H/s
            </option>
            <option>
              KH/s
            </option>
            <option>
              MH/s
            </option>
            <option>
              GH/s
            </option>
          </select>
          <ActionButton class="form__btn" @click.prevent="() => {}">
            Calculate
          </ActionButton>
        </form>
        <div class="calculator__output">
          <span class="calculator__output--sub">Estimated 24 Hour Revenue:</span>
          <h5 class="heading-tertiary calculator__output--result mt-sm">
            0.055 130 59 ETH <span>($1275)</span>
          </h5>
          <p class="calculator__output--desc">
            Revenue will change based on mining difficulty and Ethereum price.
          </p>
        </div>
      </div>
      <h4 class="heading-primary mt-100 text-center">
        Trade securely and market the high growth cryptocurrencies.
      </h4>
      <div class="grid mt-64 pb-100">
        <div class="grid__row">
          <div v-for="(item, i) in products" :key="i" class="grid__col" :class="{ selected: selectedProduct === i }" @click="toggleSelection(i)">
            <img :src="item.icon" :alt="item.name" class="product__icon">
            <div class="product__name mt-xl">
              {{ item.name }}
              <span class="product__name--short">{{ item.short }}</span>
            </div>
            <p class="text-primary product__desc mt-sm">
              {{ item.desc }}
            </p>
            <ActionButton v-show="i === selectedProduct" class="mt-md">
              Start mining
              <icon-wrapper class="chevron-right">
                <img src="~/assets/images/eva_chevron-right-outline.svg" alt="chevron right" class="icon chevron-right__icon">
              </icon-wrapper>
            </ActionButton>
            <icon-wrapper v-show="i !== selectedProduct" class="chevron-right plain mt-md">
              <img src="~/assets/images/eva_chevron-right-outline.svg" alt="chevron right" class="icon chevron-right__icon">
            </icon-wrapper>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<style lang="scss">
.plain {
  width: 6.4rem;
  height: 6.4rem;
  border-radius: 50%;
  border: 1px solid rgba(43, 7, 110, 0.20);

  &:hover {
    transform: translateY(-2px);
  }

}
.products__container {
  max-width: 100%;
  background-color: $white;
  color: $primary-color;

  .products {
    @include flex-align-center;
    flex-direction: column;

    .calculator {
        margin-top: -15rem;
        max-width: 94rem;
        width: 100%;
        padding: 4.8rem;
        border-radius: 1.6rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: $white;
        box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;

        &__output {
            align-self: flex-start;
            margin-top: 4.8rem;

            &--sub {
                font-weight: 500;
                line-height: 2.4rem;
                letter-spacing: 0.64px;
                text-transform: uppercase;
                color: $color-accent;
            }

            &--result {
                letter-spacing: 1.28px;

                span {
                    font-size: 3.2rem;
                    font-weight: 700;
                    line-height: 4.8rem;
                    letter-spacing: 1.28px;
                    color: $color-accent;
                }
            }

            &--desc {
                color: #828282;
            }
        }
    }

    .heading-primary {
        color: $primary-color;
    }

    .grid {

      &__row {
        gap: 4.5rem;

        .grid__col {
          flex-direction: column;
          align-items: center;
          padding: 4.8rem 2.4rem;
          width: 37rem;
          cursor: pointer;

          .product__icon {
            width: 8rem;
            height: 8rem;
          }

          .product__name {
            @include flex-align-center;
            gap: 8px;
            font-size: 3.2rem;
            font-weight: 700;
            line-height: 4.8rem;

            &--short {
              font-size: 1.8rem;
              font-weight: 500;
              line-height: 2.7rem;
              text-transform: uppercase;
              color: #BDBDBD;
            }
          }

          .product__desc {
            color: $white;
            text-align: center;
            line-height: 2.8rem;
            letter-spacing: 0.16px;
            color: #828282;
          }
        }

        .grid__col.selected {
          background-color: $secondary-color !important;
          color: $white;
          border-radius: 1.6rem;
          animation: fadeInBg .2s ease-out;

          .product__desc {
            color: $white !important;
          }
        }
      }
    }
  }
}

@keyframes fadeInBg {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0.5;
  }
  100% {
    opacity: 1;
  }
}

@media only screen and (max-width: 1200px) {
  .products {
    .grid__row {
      flex-wrap: wrap;
    }
  }

}

@media only screen and (max-width: 900px) {

  .products__container {
    margin: 0;
    padding: 0;

    .products {
      padding: 0;
      .calculator {
        padding: 3rem;

        .form {
          width: 100%;
          &__input {
              width: 100%;
          }
        }

        &__output {
          margin-top: 2rem;

          &--sub {
            font-size: 1.4rem;
          }

          &--result {
            font-size: 2.4rem;
            letter-spacing: .5px;

            span {
                font-size: 2.4rem;
            }
          }

          &--desc {
              font-size: 1.4rem;
          }
        }
      }

      .grid__col {
        margin: 0 2rem;
        width: 100% !important;
      }
    }
  }
}
</style>
