<script setup>
import { ref } from 'vue';
defineProps({
  icon: {
    type: String,
    required: true,
  },
});
const linkRef = ref(null);

const openLink = () => {
  const link = linkRef.value.href;
  window.open(link, '_blank');
};
</script>

<template>
  <div class="link" @click="openLink">
    <img class="link__icon" :src="icon" alt="link icon" />
    <a ref="linkRef" class="link__text" href="https://google.com" target="_blank">Learn more</a>
  </div>
</template>

<style scoped lang="scss">
.link {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 0px;
  gap: 15px;
  width: 164px;
  height: 41px;
  margin-top: 93px;
  cursor: pointer;
  transition: all 0.3s ease-in-out;

  &__text {
    text-decoration: none;
    font-size: 20px;
    line-height: 28px;
    color: inherit;
  }

  &__icon {
    transition: all 0.3s ease-in-out;
  }

  &:hover &__icon {
    transform: scale(1.1);
  }
}

@media (max-width: 900px) {
  .link {
    margin-top: 108px;
  }
  .link__text {
    display: none;
  }
}
</style>
