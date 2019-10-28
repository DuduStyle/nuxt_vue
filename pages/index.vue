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
    <el-row class="container-gutter">
      <el-col :span="6">
        <div class="grid-content bg-purple content_list">
          <div class="number">
            <span>8</span>
            <span>年</span>
          </div>
          <div class="title">
            专注设计
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple content_list">
          <div class="number">
            <span>12</span>
            <span>+</span>
          </div>
          <div class="title">
            设计师
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple content_list">
          <div class="number">
            <span>820</span>
            <span>+</span>
          </div>
          <div class="title">
            服务客户
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple content_list">
          <div class="number">
            <span>2,100</span>
            <span>+</span>
          </div>
          <div class="title">
            作品案例
          </div>
        </div>
      </el-col>
    </el-row>
    <!-- 案例作品 -->
    <div class="module_container wide">
      <el-row type="flex" align="middle" justify="space-between">
        <el-col>
          <div>FORTFOLIO</div>
          <div>作品案例</div>
        </el-col>
        <el-col class="container_category">
          <a>高端发布</a>
          <a>融资路演</a>
          <a>企业介绍</a>
          <a>招商推介</a>
          <a>可见比赛</a>
          <a>汇报总结</a>
        </el-col>
      </el-row>
      <el-row class="content_list">
        <el-col v-for="case_img in caseImages" :key="case_img" class="item_block" :span="12">
          <a target="_blank">
            <div
              class="item-img"
              :style="{backgroundImage:'url('+case_img+')'}"
            >
              <div class="item_img_mask" />
              <div class="item-icon">{{ case_img }}</div>
            </div>
            <div class="item-wrapper">
              <p class="title ellipsis">临空规划与产业招商</p>
              <p class="subtitle ellipsis">政府招商/科技风格</p>
            </div>
          </a>
        </el-col>
        <el-col :span="12">
          2
        </el-col>
        <el-col :span="12">
          3
        </el-col>
        <el-col :span="12">
          4
        </el-col>
      </el-row>
    </div>
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
      caseImages: [require("./../assets/images/case01.jpg")],
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
// 案例作品
.container_category {
  text-align: right;
  a {
    position: relative;
    display: inline-block;
    margin: 0px 25px;
    color: #6f6f6f;
    transition: all 0.3s ease-out 0s;
    font-size: 13px;
    cursor: pointer;
    &:after {
      position: absolute;
      left: 0;
      bottom: -10px;
      width: 100%;
      height: 1px;
      background-color: #232323;
      content: "";
      opacity: 0;
      transition: all 0.3s ease-out 0s;
    }
  }
  a:hover {
    color: #222;
    &:after {
      opacity: 1;
      bottom: -4px;
    }
  }
}

.content_list {
}
</style>
