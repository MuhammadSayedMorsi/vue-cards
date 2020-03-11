<template>
  <main id="main" @mousemove="mousemove">
    <section class="products">
      <Product v-for="product in products" :key="product.color" :product="product" />
    </section>
  </main>
</template>

<script>
import Product from "./product/Product";
export default {
  name: "Home",
  components: {
    Product
  },
  data() {
    return {
      products: [
        {
          title: "Click Me",
          color: "green",
          bgtext: "Adidas",
          link: "green",
          src: require("../assets/sunglass.png")
        },
        {
          title: "sunglass",
          color: "pink",
          bgtext: "Adidas",
          link: "pink",
          src: require("../assets/sunglass.png")
        },
        {
          title: "suits",
          color: "blue",
          bgtext: "Adidas",
          link: "blue",
          src: require("../assets/sunglass.png")
        }
      ]
    };
  },
  methods: {
    mousemove(el) {
      let mouseX = el.clientX;
      let mouseY = el.clientY;
      let products = document.querySelectorAll(".products .product");
      for (let i = 0; i < products.length; i++) {
        let product = products[i];
        let product_img = product.querySelector(".product-image-wrap");
        let img_x = mouseX - this.coords(product_img).x;
        let img_y = mouseY - this.coords(product_img).y;
        product_img.style.transform = `translateY(-${img_y /
          40}px) translateX(-${img_x / 40}px)`;
        // TEXT
        let bgtext = product.querySelector(".bg-text");
        let bg_x = mouseX - this.coords(bgtext).x;
        bgtext.style.transform = `translateX(${bg_x / 25}px)`;
      }
    },
    coords(e) {
      let coords = e.getBoundingClientRect();
      return {
        x: coords.left / 2,
        y: coords.top / 2
      };
    }
  }
};
</script>
<style lang="stylus">
main {
  width: 100vw;
  min-height: 100vh;
  overflow: hidden;
  background-color: #dee;
  display: flex;
  justify-content: center;
  align-items: center;

  .products {
    display: flex;
    max-width: 1280px;
    padding: 25px;
    margin: 0 auto;
  }
}
</style>