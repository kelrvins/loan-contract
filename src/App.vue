<template>
  <div id="app">
    <h1 class="contract-title">借款合同</h1>
    <p>出借方（甲方）：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>联系地址：<input
        type="text"
        style="width: 600px;"
        class="input-text"
      ></p>
    <br>
    <p>借款方（乙方）：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>联系地址：<input
        type="text"
        style="width: 600px;"
        class="input-text"
      ></p>
    <br>
    <p>乙方因<input
        type="text"
        style="width: 200px;"
        class="input-text"
      >向甲方借款，甲、乙双方经过友好协商，就借款事宜达成一致意见，特签订本合同共同遵守。</p>
    <br>
    <p>1. 经双方友好协商，乙方向甲方借取人民币 <input
        type="text"
        v-model="money"
        style="width: 100px; text-align: center;"
        class="input-text"
      > 元（大写 <input
        type="text"
        placeholder="根据数字计算，太长就..."
        v-model="moneyCH"
        style="width: 220px; text-align: center;"
        class="input-text"
      > ）。</p>
    <p>2. 乙方就上述借款按<input
        type="text"
        style="width: 150px;"
        class="input-text"
      >的标准向甲方支付利息。利息计算以甲方对应款项支付至乙方指定收款账号之日起算，至对应款项归还或提前归还至甲方账户之日止。乙方指定的收款账号为：</p>
    <p>开户名：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>开户行：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>账号：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>3.本借款期限为<input
        type="text"
        style="width: 50px; text-align: center;"
        class="input-text"
      >年，自乙方指定账户收到对应款项之日起算。但乙方可在任意时间提前还款。提前还款部分，自款项归还至甲方指定账号之日停止计息。甲方指定的回款账号为：</p>
    <p>开户名：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>开户行：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>账号：<input
        type="text"
        style="width: 400px;"
        class="input-text"
      ></p>
    <p>4. 任一方变更指定账号的，需提前3个工作日通知对方。</p>
    <p>5. 借款方如逾期不还借款，贷款方有权追回借款，并按银行规定加收罚息。借款方提前还款的，应按规定减收利息。</p>
    <p>6. 乙方应当保证借款用途的合法性，任何情况下，甲方不承担乙方借款用途导致的风险。</p>
    <p class="strong-text">7. 本合同除签名及日期外，其他内容手写无效。后续变更及确认事宜应当通过双方指定邮箱或者另行签署书面协议为准。</p>
    <p>甲方邮箱:<input
        type="text"
        style="width: 200px; margin-right: 100px;"
        class="input-text"
      >乙方邮箱:<input
        type="text"
        style="width: 200px;"
        class="input-text"
      ></p>
    <p>8. 因本协议产生的纠纷，双方应友好协商解决，协商不成的，由甲方所在地人民法院管辖。</p>
    <p>9. 本合同一式两份，甲乙双方各执一份，自双方签字后生效，具有同等法律效力。</p>
    <div class="sign-area-wrap">
      <div class="sign-area">
        <div class="sign-area-title">甲方：</div>
        <br>
        <br>
        <div class="sign-area-date">年  月  日</div>
      </div>
      <div class="sign-area">
        <div class="sign-area-title">乙方：</div>
        <br>
        <br>
        <div class="sign-area-date">年  月  日</div>
      </div>
    </div>
  </div>
</template>

<script>
import {digitUppercase} from './digitUppercase'
export default {
  name: "app",
  data() {
    return {
      money: '',
      moneyCH: ''
    }
  },
  watch: {
    money(val) {
      this.moneyCH = Number(val)? digitUppercase(val):''
    }
  }
};
</script>

<style scoped>
#app {
  font-family: -apple-system, BlinkMacSystemFont, Helvetica Neue, PingFang SC,
    Microsoft YaHei, Source Han Sans SC, Noto Sans CJK SC, WenQuanYi Micro Hei,
    sans-serif;
  font-size: 18px;
  font-family: cursive;
  font-weight: bolder;
  -webkit-tap-highlight-color: rgba(26, 26, 26, 0);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 842px;
  margin: 0 auto 50px;
}
h1 {
  text-align: center;
  margin: 50px 0;
}
p {
  text-indent: 2em;
  margin: 5px 0;
  line-height: 1.5;
}
.strong-text {
  color: #000;
  text-decoration: underline;
}
.input-text {
  display: inline-block;
  min-width: 30px;
  box-sizing: border-box;
  font-weight: border;
  padding: 0 10px;
  outline: none;
  border: none;
  border-bottom: 1px solid #1a1a1a;
}
.sign-area-wrap{
  margin-top: 50px;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding-left: 50px;
}
.sign-area{
  width: 400px;
}
.sign-area-date{
  text-align: center;
  letter-spacing: 10px;
}
</style>
