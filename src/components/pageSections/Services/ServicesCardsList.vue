<script setup>
import ServiceCard from './ServiceCard.vue';
import ButtonComponent from '../../ButtonComponent.vue';
import cardsData from '/src/data/servicesCards';
</script>

<template>
  <div class="services__cards">
    <ServiceCard
      v-for="(card, index) of cardsData"
      :key="index"
      :color="card.color"
      :img="card.imgSrc"
    >
      <template #first>{{ card.firstLine }}</template>
      <template #second>{{ card.secondLine }} </template>
    </ServiceCard>
  </div>
  <div class="services__proposal-card">
    <div class="proposal-card__text">
      <h3 class="text__title">Let’s make things happen</h3>
      <p class="text__paragraph">
        Contact us today to learn more about how our digital marketing services can help your
        business grow and succeed online.
      </p>
      <ButtonComponent class="proposal-card__button" color="black">
        Get your free proposal
      </ButtonComponent>
    </div>
    <img
      class="proposal-card__img"
      src="/assets/services-cards/services-Illustration.png"
      alt="proposal illustration"
    />
  </div>
</template>

<style scoped lang="scss">
@import '../../../_config.scss';
.services__cards {
  @include flex-row;
  flex-wrap: wrap;
  gap: 40px;
}

.services__proposal-card {
  margin: 124px 0 24px 0;
  @include flex-row;
  align-items: center;
  padding: 0px 60px;
  gap: 205px;
  width: 1240px;
  height: 347px;
  background: $grey;
  border-radius: 45px;

  .proposal-card__img {
    width: 359px;
  }

  .proposal-card__text {
    height: 227px;
    width: 480px;
    gap: 26px;

    .text__title {
      font-weight: 500;
      font-size: 30px;
      line-height: 38px;
    }

    .text__paragraph {
      font-weight: 400;
      font-size: 18px;
      line-height: 23px;
      margin: 26px 0;
    }
  }
}

@media (max-width: 900px) {
  .services {
    @include flex-column;
    align-items: center;
  }

  .services__cards {
    width: 100%;
    align-items: center;
    justify-content: center;
    gap: 30px;
  }

  .services__proposal-card {
    margin: 70px auto 0;
    padding: 50px;
    width: 100%;
    max-width: 390px;
    height: auto;

    .proposal-card__img {
      display: none;
    }

    .proposal-card__button {
      width: 100%;
    }

    .proposal-card__text {
      height: auto;

      .text__title {
        font-size: 26px;
        line-height: 33px;
      }

      .text__paragraph {
        font-size: 16px;
        line-height: 24px;
        margin: 20px 0;
        width: 100%;
      }
    }
  }
}

@media (min-width: 901px) and (max-width: 1439px) {
  .services__cards {
    width: 100%;
    align-items: center;
    justify-content: center;
    gap: 30px;
  }

  .services__proposal-card {
    width: 100%;
    margin: 70px auto 0;
    padding: 50px;
    gap: 0;
    justify-content: space-between;
  }
}
</style>
