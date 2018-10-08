# vue1
实现九宫格抽奖活动
<template>
 <div class="luckDraw">
  <title-bar :title="title"></title-bar>
  <div class="container">
   <div class="turntable-wrapper">
    <div class="luck-wrapper">
     <p class="integral">我的积分: <span>1000</span></p>
     <ul class="nineGrid">
      <li class="row">
       <div v-for="(n, key) in 3" :key="n" :class="index === key ? `active` : ``">
        <div class="wrapper">
         <img src="../../assets/luck-icon.png" alt="">
         <p>8金转</p>
        </div>
        <div class="mask"></div>
       </div>
      </li>
      <li class="row">
       <div :class="index === 7 ? 'active': ''">
        <div class="wrapper">
         <img src="../../assets/luck-icon.png" alt="">
         <p>128金转</p>
        </div>
        <div class="mask"></div>
       </div>
       <div class="getLuck" @click="startLottery">
        <p>立即<br>抽奖</p>
       </div>
        <div :class="index === 3 ? 'active': ''">
        <div class="wrapper">
         <img src="../../assets/luck-icon.png" alt="">
         <p>128金转</p>
        </div>
        <div class="mask"></div>
       </div>
      </li>
      <li class="row">
       <div v-for="(n, key) in 3" :key="n" :class="index === 6-key ? `active` : ``">
        <div class="wrapper">
         <img src="../../assets/luck-icon.png" alt="">
         <p>256金转</p>
        </div>
        <div class="mask"></div>
       </div>
      </li>
     </ul>
    </div>

    <p class="share">分享领积分 <i class="icon-go"></i></p>

    <div class="rule">
     <p class="rule-title">活动规则</p>
     <ul class="rule-main">
      <li>1、活动时间：2017年9月8日起；</li>
      <li>2、活动期间，股事汇用户每次抽奖消耗20积分，抽奖次数不限</li>
      <li>3、金钻可用于向投顾提问、送礼、赞赏；</li>
      <li>4、积分赚取：每日签到、分享文章/问答/直播间、点赞、金钻充值均可获得积分哦</li>
      <li>5、活动最终解释权归股事汇所有。</li>
     </ul>
    </div>

    <div></div>
   </div>

   <LuckToast :showToast="showToast" :toastType="toastType" @closeToast="closeToast" @startLottery="startLottery"></LuckToast>
  </div>
 </div>
</template>
