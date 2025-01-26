<template>
  <header>
    <a href="vs24-c.github.io/home-work-vue/" class="logo">
      <img :src="logo.img" alt="" />
    </a>
    <nav class="menu">
      <ul>
        <li><a href="">Home</a></li>
        <li><a href="">About</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
import logo from '../assets/logo.png';

export default {
  name: 'HeaderComp',
  data() {
    return {
      logo: { img: logo },
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 30px;
}
.logo {
  position: relative;
  width: 30px;
  padding-bottom: 30px;
  img {
    position: absolute;
    inset: 0;
    height: 100%;
    width: 100%;
    object-fit: contain;
  }
}
.menu {
  ul {
    display: flex;
    align-items: center;
    gap: 15px;

    li {
      list-style-type: none;
      a {
        font-size: 18px;
        font-weight: 500;
        line-height: 1.5;
        color: orchid;
        text-decoration: none;
      }
    }
  }
}
</style>
