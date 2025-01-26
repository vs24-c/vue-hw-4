<template>
  <header-comp />
  <h1>Home Work 4</h1>
  <compare-list />
  <last-prod :products="products" />
  <hr />
  <messenger-comp />
</template>

<script>
import CompareList from './components/CompareList.vue';
import HeaderComp from './components/HeaderComp.vue';
import LastProd from './components/LastProd.vue';
import MessengerComp from './components/MessengerComp.vue';

//-----------img-----------
import samsung from './assets/tel-1.jpg';
import toshiba from './assets/tel-2.jpg';
import schrank from './assets/schwarz-schrank.jpg';
import likeimg from './assets/like.svg';

export default {
  name: 'App',
  components: {
    CompareList,
    HeaderComp,
    LastProd,
    MessengerComp,
  },
  data() {
    return {
      products: [
        {
          img: samsung,
          icon: likeimg,
          title: 'Samsung 4K UHD TV',
          review: 'Immersive viewing experience with vibrant colors.',
          stock: 'In stock',
          price: 699.99,
          description:
            'Samsung 4K UHD TV delivers stunning picture quality with deep contrasts and vibrant colors. Ideal for movie nights and gaming enthusiasts.',
        },
        {
          img: toshiba,
          icon: likeimg,
          title: 'Toshiba 4K Smart TV',
          review: 'Exceptional picture quality and seamless streaming.',
          stock: 'Limited stock',
          price: 1199.99,
          description:
            'Experience cinematic visuals with Toshiba’s 4K Smart TV. Enjoy your favorite shows and movies in stunning clarity with built-in streaming apps.',
        },
        {
          img: schrank,
          icon: likeimg,
          title: 'Schrank mit Schreibtisch',
          review: 'Durable and stylish',
          stock: 'In stock',
          price: 29.99,
          description:
            'A multifunctional Schrank with an integrated desk, perfect for small spaces. Durable and stylish, it complements modern interiors.',
        },
      ],
      counter: 0,
    };
  },
  methods: {},
};
</script>

<style>
#app {
  margin-bottom: 100px;
}
</style>
