<template>
  <div>
    <!-- banner -->
    <el-carousel class="banner" trigger="click" :height="clientHeight">
      <el-carousel-item v-for="item in images" :key="item">
        <div
          class="item_bg image"
          style="backgroundImage: url('http://resources.jsmo.xin/templates/upload/16886/201910/1571023199395.jpg')"
        >
          <!-- <img :src="item"> -->
        </div>
      </el-carousel-item>
    </el-carousel>
    <!-- 数字介绍 -->
    <el-row class="container-gutter ">
      <el-col :span="6">
        <div class="grid-content bg-purple content_list">
          <div class="number">
             <span>8</span>
            <span>年</span>
          </div>
          <div class="title">专注设计</div>
        </div>
      </el-col>
      <el-col :span="6">
         <div class="grid-content bg-purple content_list">
          <div class="number">
             <span>12</span>
            <span>+</span>
          </div>
          <div class="title">设计师</div>
        </div>
      </el-col>
      <el-col :span="6">
         <div class="grid-content bg-purple content_list">
          <div class="number">
             <span>820</span>
            <span>+</span>
          </div>
          <div class="title">服务客户</div>
        </div>
      </el-col>
      <el-col :span="6">
         <div class="grid-content bg-purple content_list">
          <div class="number">
            <span>2,100</span>
            <span>+</span>
          </div>
          <div class="title">作品案例</div>
        </div>
      </el-col>
    </el-row>
  </div>
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
      clientHeight: "600px"
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

<style lang="scss">
.banner {
  .item_bg.image {
    width: 100%;
    height: 100%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    // background-image: url(http://resources.jsmo.xin/templates/upload/16886/201910/1571023199395.jpg);
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
}
.container-gutter {
  padding: 100px 0;
  .content_list {
    .number {
      text-align: center;
    }
    .title {
      text-align: center;
    }
  }
}
</style>
