<template>
  <div v-show="showFlag" class="payMoney">
    <div class="confirmOrder">
      <span class="back">
        <i class="icon-arrow_lift" @click="hidePay"></i>
      </span>
      <span class="text">确认订单</span>
    </div>
    <div class="address">
      <div class="personalInformation">
        <span class="name">董鲜悦</span>
        <span class="gender">女士</span>
        <span class="phoneNumber">13219015361</span>
      </div>
      <div class="adressInformation">电子科技大学沙河校区物理电子学院512</div>
    </div>
    <split></split>
    <div class="deliveryTime">
      <div class="title">送达时间</div>
      <div class="text">
        <div class="fast">
          <div class="txt">尽快送达&nbsp|&nbsp预计24:00</div>
        </div>
        <div class="desc">当前恶劣天气，暂不享受超时赔付</div>
      </div>
    </div>
    <split></split>
    <div class="paymentMethod">
      <div class="text">支付方式</div>
      <div class="method">在线支付</div>
    </div>
    <split></split>
    <div class="information">
      <div class="sellerName"></div>
      <div class="selectFood">
        <ul>
          <li class="food-item" v-for="item in selectFoods"></li>
        </ul>
      </div>
      <div class="deliveryPrice"></div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import split from '../../components/split/split.vue';

  export default {
    props: {
      selectFoods: {
        type: Array,
        default() {
          return [];
        }
      }
    },
    data() {
      return {
        showFlag: false
      };
    },
    methods: {
      showPay() {
        this.showFlag = true;
      },
      hidePay() {
        this.showFlag = false;
      }
    },
    components: {
      split
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .payMoney {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    bottom: 48px;
    background: #fff;
    z-index: 40;
  }
  .payMoney .confirmOrder {
    line-height: 50px;
    background: rgb(0,160,220);
    color: #fff;
    font-size: 20px;
    width: 100%;
    height: 50px;
  }
  .payMoney .confirmOrder .back {
    margin-left: 10px;
    display: inline-block;
  }
  .payMoney .confirmOrder .back .icon-arrow_lift {
    display: inline-block;
    padding: 10px;
    margin-top: 5px;
    vertical-align: top;
  }
  .payMoney .confirmOrder .text {
    display: inline-block;
    vertical-align: top;
  }
  .payMoney .address {
    padding: 0 40px;
    height: 50px;
    width: 100%;
  }
  .payMoney .address .personalInformation {
    height: 20px;
    margin: 10px auto;
    font-size: 0;
  }
  .payMoney .address .personalInformation .name {
    /*display: inline-block;*/
    line-height: 20px;
    margin-right: 5px;
    font-size: 16px;
    font-weight: 700;
  }
  .payMoney .address .personalInformation .gender {
    margin-right: 10px;
    line-height: 20px;
    font-size: 14px;
    font-weight: 600;
  }
  .payMoney .address .personalInformation .phoneNumber {
    font-size: 14px;
    line-height: 20px;
  }
  .payMoney .address .adressInformation {
    height: 10px;
    line-height: 10px;
    font-size: 12px;
    color: #999;
  }
  .payMoney .deliveryTime {
    display: flex;
    width: 100%;
    height: 80px;
  }
  .payMoney .deliveryTime .title {
    flex: 0 0 80px;
    padding-left: 20px;
    height: 80px;
    line-height: 80px;
  }
  .payMoney .deliveryTime .text {
    flex: 1;
    margin-right: 30px;
  }
  .payMoney .deliveryTime .text .fast {
    height: 40px;
    width: 100%;
    line-height: 40px;
    border-bottom: 1px solid #ddd;
  }
  .payMoney .deliveryTime .text .fast .txt {
    float: right;
    color: rgb(0,160,220);
    font-size: 14px;
    font-weight: 600;
  }
  .payMoney .deliveryTime .text .desc {
    float: right;
    height: 40px;
    line-height: 40px;
    font-size: 12px;
    color: #999;
  }
  .payMoney .paymentMethod {
    height: 40px;
    line-height: 40px;
    margin: auto 15px;
  }
  .payMoney .paymentMethod .text {
    display: inline-block;
    float: left;
  }
  .payMoney .paymentMethod .method {
    display: inline-block;
    float: right;
  }
</style>
