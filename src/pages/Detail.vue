<template>
  <div class="detail" id="detail">
    <div class="detail-wrap">
      <div class="detail-intro">
        <p>今日认购总额（元）</p>
        <p class="sum">￥20,000</p>
      </div>
      <ul class="detail-total">
        <li class="btn"><em>借款金额</em><b>￥200,000</b></li>
        <li class="btn"><em>起投金额</em><b>￥1000</b></li>
        <li class="btn"><em>借款期限</em><b>30天</b></li>
        <li class="btn"><em>利率</em><b>10%</b></li>
      </ul>
      <div class="detail-items">
        <div class="detail-item title" @click="toggle($event)">
          <a class="grow tit" href="javascript:;"><i class="icon iconfont">&#xe655;</i>项目详情</a>
          <a class="grow btn" href="javascript:;"><i class="icon iconfont">{{show ?'&#xe65e;':'&#xe65f;'}}</i></a>
        </div>
        <div class="detail-item info" v-show="show">
          <p><span>融资方：</span>融资方为八戒宝战略合作机构：中汇银和融资租赁有限公司，注册资本3000万美元。业务涉及融资租赁业务、租赁业务、向国内外购买租赁财产、租赁财产的残值处理及维修、租赁交易的咨询。中汇银和融资租赁有限公司拥有高效的经营管理架构、完善的财务治理结构以及较强的风险管控能力，努力实现组织系统化、决策科学化、管理规范化和作业标准化。中汇银和融资租赁有限公司将全程监控企业资金流向，并实地勘验该企业真实运营情况，保障资金安全，并将回款优先偿还项目本息。</p>
          <p><span>借款方：</span>借款企业成立于2005年，注册资本1100万元。主营业务：交通安全设施销售与安装；公路工程施工、园林绿化工程设计及施工。企业经营近10年，产品遍布全省十多个地、市、区，是全省较早的专业性厂家，业绩在同行中位属前列。</p>
          <p><span>资金托管：</span>投资资金由第三方机构托管，资金账户与八戒宝公司账户风险隔离。</p>
          <p><span>还款及收益说明：</span>天天赚采用“每日返息，到期还本”的收益方式，即每日赚得固定利息，并由八戒宝先行垫付。最后一期回收全部本金。</p>
          <p><span>加入规则：</span>投资者可在八戒宝官网进行充值投资。认购金额最低50元，50元递增，本期认购无上限，直至投满为止。</p>
          <p><span>相关费用：</span>天天赚产品0加入费，用户只需承担提现所产生的费用。单笔提现金额小于5万元的，每笔收取1元提现手续费；单笔提现金额大于等于5万元，每笔收取5元提现手续费。</p>
        </div>
      </div>
      <div class="detail-items">
        <div class="detail-item title" @click="toggle($event)">
          <a class="grow tit" href="javascript:;"><i class="icon iconfont">&#xe659;</i><em>认购记录</em></a>
          <a class="grow btn" href="javascript:;"><i class="icon iconfont">&#xe65f;</i></a>
        </div>
        <div class="detail-item info" v-show="show">
          <table class="tab-wrap" width="100%" border="0" cellspacing="0" cellpadding="0">
            <tr>
              <th>用户</th>
              <th>日期</th>
              <th>金额</th>
            </tr>
            <tr>
              <td>138****1122</td>
              <td>11-21</td>
              <td>50,000</td>
            </tr>
            <tr>
              <td>158****3366</td>
              <td>11-28</td>
              <td>80,000</td>
            </tr>
            <tr>
              <td>138****1122</td>
              <td>11-21</td>
              <td>50,000</td>
            </tr>
            <tr>
              <td>158****3366</td>
              <td>11-28</td>
              <td>80,000</td>
            </tr>
            <tr>
              <td>138****1122</td>
              <td>11-21</td>
              <td>50,000</td>
            </tr>
            <tr>
              <td>158****3366</td>
              <td>11-28</td>
              <td>80,000</td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "detail",
    data() {
      return {
        title: '产品详情',
        show: false
      }
    },
    mounted() {
      this.$parent.title = this.title;
      this.initScroll();
    },
    methods: {
      toggle(event) {
        if (!event._constructed) return;
        // this.show = !this.show;
        var info = event.currentTarget.parentNode.children[1];
        if(info.style.display=='none'){
          info.style.display='block'
        }else{
          info.style.display='none'
        }
        this.$nextTick(function () {
          detail_scroll.refresh();
        });
      },
      initScroll(){
        window.detail_scroll = new this.BScroll('#detail', {
          preventDefault: true,
          click: true
        });
      }
    }
  }
</script>