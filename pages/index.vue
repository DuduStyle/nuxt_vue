<template>
  <!-- <div class="container"> -->
  <!-- banner -->
  <el-carousel trigger="click" :height="clientHeight">
    <el-carousel-item v-for="item in images" :key="item">
      <img :src="item">
    </el-carousel-item>
  </el-carousel>
  <!-- </div> -->
</template>

<script>
export default {
  data() {
    return {
      /**
       * 轮播图列表
       */
      images: [
        require("./../assets/images/banner01.jpg"),
        require("./../assets/images/banner02.jpg")
      ],
      clientHeight: '600px'
    };
  },
  mounted() {
    // 动态设置背景图的高度为浏览器可视区域高度
    // 首先在Virtual DOM渲染数据时，设置下背景图的高度．
    this.clientHeight = `${document.documentElement.clientHeight}px`;
    // 然后监听window的resize事件．在浏览器窗口变化时再设置下背景图高度．
    const that = this;
    window.onresize = function temp() {
      that.clientHeight = `${document.documentElement.clientHeight}px`;
    };
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>
