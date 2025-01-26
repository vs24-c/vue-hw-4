<template>
  <h3>Last viewed products</h3>
  <div class="page__cards">
    <div v-for="(product, ind) in products" :key="ind" class="card">
      <div class="like"><img :src="product.icon" alt="" /></div>
      <div class="card__image">
        <img :src="product.img" alt="" />
      </div>
      <div class="card__description">
        <h4>{{ product.title }}</h4>
        <p>{{ product.review }}</p>
        <div class="card__footer">
          <span class="stock">{{ product.stock }}</span>
          <span class="price">{{ product.price }} $</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LastProd',

  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.page__cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  grid-template-rows: auto;
  align-items: center;
  gap: 15px;
}
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 10px;
  padding: 10px;
  padding-top: 40px;
}
.card__image {
  position: relative;
  width: 100%;
  padding-bottom: 250px;
  img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    object-fit: cover;
  }
}
.like {
  position: absolute;
  top: 0;
  right: 15px;
  width: 30px;
  height: 30px;
  z-index: 3;
  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
}
.card__description {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  gap: 5px;
}
.card__footer {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.stock {
  color: blueviolet;
}
.price {
  color: red;
  font-weight: bold;
}
</style>
