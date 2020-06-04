<template>
  <div class="page introductions">
    <h1 class="title">{{ $store.state.data.route[id] }}</h1>
    <div class="pagebody">
      <div class="selfIntroduction">
        <span class="left">教育经历:</span>
        <div v-for="(item,index) in $store.state.data.website.description" :key="index">
          <span>{{item.school}}</span>
          <span>{{item.major}}</span>
          <span>{{item.data}}</span>
          <span>{{item.education}}</span>
        </div>
        <span class="left">荣誉奖励:&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;发表专利1篇 | 三等奖学金 | 英语六级 | 中共党员</span>
        <span class="left">个人评价 :</span>
        <span
          class="left"
        >&nbsp;&nbsp;&nbsp;&nbsp;学习能力较强;平时都在 github,谷歌,stackoverflow 等网站解决问题;具备正常的沟通能力和组织能力,喜欢编程,热衷前端岗位.</span>
      </div>
      <div class="selfInformations">
        <div class="infoRow">
          <div class="placeholder"></div>
          <div v-for="(v, i) in $store.state.data.website.infomations" :key="i" class="infoItem">
            <!-- <div > -->
            <img :src="v.icon" :alt="v.key" :title="v.key" class="icon" />
            <p>{{ v.value }}</p>
            <!-- </div> -->
          </div>

          <div class="placeholder"></div>
        </div>
        <div class="infoRow infoCol">
          <div class="infoItem" v-for="(v, i) in $store.state.data.website.infomations" :key="i">
            <img :src="v.icon" class="icon" />
            <p>{{ v.key + '：' + v.value }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "introductions",
  props: ["id"]
};
</script>

<style lang="less" scoped>
@import "index.less";
</style>
