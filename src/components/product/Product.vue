<template>
  <div class="product">
    <div :class="'product-inner ' + product.color">
      <div class="product-text-wrap">
        <h2 class="bg-text">{{product.bgtext}}</h2>
      </div>
      <div class="product-image-wrap">
        <img :src="product.src" alt="product-img" />
      </div>
      <div class="product-detail">
        <router-link to="/post">
          <h2 :class="'Title-card ' + product.link">{{ product.title }}</h2>
        </router-link>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Mollitia laborum laboriosam, doloremque quam assumenda placeat iusto perspiciatis quia modi culpa!</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "product",
  props: ["product"]
};
</script>


<style lang="stylus">
.product {
  flex: 1 1 33.333%;
  width: 100%;
  padding: 25px;
  transition: all 0.4s ease-in-out;
  cursor: pointer;

  &:hover {
    transform: scale(1.1);

    .Title-card.green {
      border-bottom: 2px solid #24d484;
      width: 100px;
    }

    .Title-card.pink {
      border-bottom: 2px solid #f444a4;
      width: 103px;
    }

    .Title-card.blue {
      border-bottom: 2px solid #2474c4;
      width: 60px;
    }
  }
}

.product-inner {
  position: relative;
  padding: 25px;
  background-color: white;
  box-shadow: 0px 0px 16px rgba(0, 0, 0 0.25);
  perspective: 1000px;

  &.green {
    background-image: linear-gradient(to bottom right, #24d484, #116423);
  }

  &.blue {
    background-image: linear-gradient(to bottom left, #24d484, #2474c4 70%);
  }

  &.pink {
    background-image: linear-gradient(to bottom right, #f444a4, #1168d4);
  }

  .product-text-wrap {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 0;
    overflow: hidden;
    perspective: 1000px;

    h2 {
      color: #313131;
      font-size: 90px;
      font-weight: bold;
      opacity: 0.2;
      padding-left: 5px;
      transform-origin: center;
    }
  }

  .product-image-wrap {
    position: relative;
    z-index: 1;
    text-align: center;
    transform-origin: center;
    margin: 30px 0;

    img {
      width: 50%;
      height: 170%;
      filter: drop-shadow(0px 0px 12px rgba(0, 0, 0, 0.25));
    }
  }

  .product-detail {
    position: relative;
    z-index: 10;
    background-color: #fff;
    padding: 25px;
    margin: 0px -25px -25px;

    .Title-card {
      font-size: 24px;
      font-weight: 700px;
      color: #676767;
      margin-bottom: 15px;
    }

    p {
      font-size: 14px;
      line-height: 1.5;
      font-weight: 300;
      color: #070707;
    }
  }

  // removeTextDecoration
  a {
    text-decoration: none;
  }
}
</style>
