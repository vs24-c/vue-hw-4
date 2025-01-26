<template>
  <h4>{{ title }}</h4>
  <p>{{ text }} {{ counter }}</p>
  <div class="card__box">
    <div v-for="(i, ind) in imagePhone" :key="ind" class="card__img">
      <img :src="i.img" alt="" />
    </div>
  </div>
</template>

<script>
import blackImage from '../assets/iphone-16-black.jpeg';
import whiteImage from '../assets/iphone-16-milky.jpeg';
import silverImage from '../assets/iphone-16-silver.jpeg';

export default {
  name: 'CompareList',
  data() {
    return {
      title: 'Mobile Phones',
      text: 'Quantity products',
      imagePhone: [
        { img: blackImage },
        { img: whiteImage },
        { img: silverImage },
      ],
    };
  },
  computed: {
    counter() {
      return this.imagePhone.length;
    },
  },
};
</script>

<style lang="scss" scoped>
.card__box {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  grid-template-rows: auto;
  justify-content: center;
  align-items: center;
  gap: 15px;
}
.card__img {
  position: relative;
  width: 100%;
  padding-bottom: 240px;
  img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    object-fit: contain;
  }
}
</style>
