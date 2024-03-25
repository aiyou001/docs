最主要是呼吸动画 根据透明度 u-skeleton--animate

![An image](./assets/骨架屏.gif)

```vue
<template>
  <div class="skelecton">
    <div class="u-skeleton--animate">
      <div class="head">
        <div class="head_search flex-row">
          <div class="round"></div>
          <div class="flex search"></div>
          <div class="round"></div>
        </div>
        <div class="head_nav">
          <div class="nav_row flex-row just-between">
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
          </div>
          <div class="nav_row flex-row just-between mt20">
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
            <div class="per">
              <div class="sqare"></div>
              <div class="line"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="swpper">
        <div class="indicator flex-row just-around">
          <div class="round"></div>
          <div class="round"></div>
          <div class="round"></div>
        </div>
      </div>

      <div class="conent1 flex-row">
        <div class="round"></div>
        <div class="flex"></div>
        <div class="line"></div>
      </div>

      <div class="conent2">
        <div class="picture">
          <div class="round"></div>
        </div>
        <div class="left"></div>
        <div class="right"></div>
        <div class="body flex-col">
          <div class="line mt20" style="height:18px; width:50%"></div>
          <div class="line mt10" style="height:18px; width:30%"></div>
          <div class="line mt20" style="height:10px; width:45%"></div>
          <div class="line mt10" style="height:15px; width:30%"></div>
          <div class="line mt20" style="height:2px; width:80%"></div>
          <div class="line mt20" style="height:10px; width:40%"></div>
          <div class="line mt10" style="height:18px; width:30%"></div>
          <div class="line mt20 mb20" style="height:35px; width:35%; borderRadius:10px"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
      };
    },
  };
</script>

<style lang="scss" scoped>
  .skelecton {
    background-color: #f8f8f8;
    width: 100vw;
    height: 100vh;
  }

  .head {
    position: relative;
    width: 100vw;
    height: 200px;
    background-color: #e5e5e5;
    border-radius: 0 0 20px 20px;

    .head_search {
      position: absolute;
      margin: 0 15px;
      width: calc(100vw - 30px);
      top: 20px;
      left: 0;

      .round {
        width: 25px;
        height: 25px;
        background-color: #fff;
        border-radius: 100%;
      }

      .search {
        background-color: #fff;
        height: 30px;
        margin: 0 15px;
        border-radius: 30px;
      }
    }

    .head_nav {
      position: absolute;
      left: 0;
      bottom: -15%;
      margin: 0 20px;
      padding: 20px 25px;
      width: calc(100vw - 40px);
      background-color: #fff;
      border-radius: 10px;
      box-sizing: border-box;

      .nav_row {
        .per {
          .sqare {
            width: 30px;
            height: 30px;
            border-radius: 5px;
            background-color: #e5e5e5;
          }

          .line {
            margin-top: 8px;
            width: 30px;
            height: 7px;
            background-color: #e5e5e5;
            border-radius: 20px;
          }
        }
      }
    }
  }

  .swpper {
    position: relative;
    margin: 60px 15px 0 15px;
    width: calc(100vw - 30px);
    height: 120px;
    background-color: #e5e5e5;
    border-radius: 10px;

    .indicator {
      position: absolute;
      left: 50%;
      bottom: 10%;
      transform: translateX(-50%);
      width: 50px;

      .round {
        width: 8px;
        height: 8px;
        background-color: #fff;
        border-radius: 100%;
      }
    }
  }

  .conent1 {
    background-color: #fff;
    width: calc(100vw - 30px);
    margin: 20px 15px 0 15px;
    padding: 5px 10px;
    box-sizing: border-box;
    border-radius: 5px;

    .round {
      width: 25px;
      height: 25px;
      background-color: #e5e5e5;
      border-radius: 100%;
    }

    .line {
      width: 85%;
      height: 12px;
      background-color: #e5e5e5;
      border-radius: 15px;
    }
  }

  .conent2 {
    position: relative;
    background-color: #fff;
    width: calc(100vw - 30px);
    margin: 20px 15px 0 15px;
    // padding: 5px 10px;
    box-sizing: border-box;
    border-radius: 5px;
    overflow: hidden;

    .picture {
      position: relative;
      width: 100%;
      height: 100px;
      background-color: #e5e5e5;

      .round {
        position: absolute;
        left: 4%;
        bottom: 10%;
        width: 15px;
        height: 15px;
        background-color: #fff;
        border-radius: 100%;
      }
    }

    .line {
      width: 85%;
      height: 12px;
      background-color: #e5e5e5;
      border-radius: 15px;
    }

    .body {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .left {
      position: absolute;
      width: 20px;
      height: 50px;
      background-color: #e5e5e5;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
      border-radius: 0 10px 10px 0;
    }

    .right {
      position: absolute;
      width: 20px;
      height: 50px;
      background-color: #e5e5e5;
      right: 0;
      top: 50%;
      transform: translateY(-50%);
      border-radius: 10px 0 0 10px;
    }
  }

  .line {
    width: 85%;
    height: 12px;
    background-color: #e5e5e5;
    border-radius: 15px;
  }

  .u-skeleton--animate {
    -webkit-animation: u-skeleton-blink 1.2s ease-in-out infinite;
    animation: u-skeleton-blink 1.2s ease-in-out infinite;
  }

  @-webkit-keyframes u-skeleton-blink {
    50% {
      opacity: 0.5;
    }
  }

  @keyframes u-skeleton-blink {
    50% {
      opacity: 0.5;
    }
  }
</style>

```
