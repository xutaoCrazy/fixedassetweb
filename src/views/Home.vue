<template>
  <div class="fixedasstcontain">
    <div class="content-main-asset">
      <div class="title">{{title}}资产使用轨迹</div>
      <div v-if="trace==true" class="gj">暂无资产使用轨迹</div>
      <div class="content-main-wrap" v-else v-for="item in list" :key="item.gjid">
        <div class="main-left">
          <div class="date">
            <i class="fa fa-calendar"></i>
          </div>
          <div class="time">{{item.inittime | formatDate('yyyy-MM-dd')}}</div>
          <div class="time">{{item.inittime | formatDate('hh:mm:ss')}}</div>
        </div>
        <div class="main-right">
          <div class="contentassignment" style="font-weight: 700;color: #676a6c;">{{item.fcaName}}</div>
          <div class="contentassignment" v-if="item.bce01e">
            <span>登记人:</span>
            {{item.bce01e}}
          </div>
          <div class="contentassignment" v-if="item.bce01a">
            <span>领用人:</span>
            {{item.bce01a}}
          </div>
          <div class="contentassignment" v-if="item.fsName">
            <span>发送人:</span>
            {{item.fsName}}
          </div>
          <div class="contentassignment" v-if="item.jsName">
            <span>接收人:</span>
            {{item.jsName}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import 'font-awesome/css/font-awesome.min.css'
import '@/filters/index'
export default {}
</script>

<style scoped>
.fixedasstcontain {
  border: solid 1px #e4e4e4;
  height: 100%;
}
#app {
  width: 100%;
  background: #f9f9f9;
  font-size: 14px;
  color: #000;
}
.content-main-wrap {
  display: flex;
}
.content-main-asset {
  padding: 0px 0px 20px 0px;
  border-width: 1px 0px;
}
.content-main-asset .main-left {
  width: 130px;
  padding-bottom: 10px;
}
.content-main-asset .main-right {
  border-left: 1px solid #e7eaec;
  border-top: 1px solid #e7eaec;
  padding-top: 10px;
  min-height: 60px;
  width: calc(100% - 130px);
  display: flex;
  flex-direction: column;
}
.content-main-asset .date i {
  padding: 5px;
  width: 30px;
  text-align: center;
  border-top: 1px solid #e7eaec;
  border-bottom: 1px solid #e7eaec;
  border-left: 1px solid #e7eaec;
  background: #f8f8f8;
  color: #000;
}
.content-main-asset .date {
  text-align: right;
  margin-bottom: 5px;
  color: #000;
}
.content-main-asset .time {
  text-align: right;
  padding-right: 15px;
  height: 20px;
  line-height: 20px;
  font-size: 14px;
  color: #000;
}
.content-main-asset .contentassignment {
  height: 25px;
  line-height: 20px;
  text-align: left;
  padding-right: 5px;
  padding-left: 10px;
  color: #000;
  font-size: 14px;
}
.title {
  color: #000;
  font-size: 14px;
  padding: 5px;
  border-bottom: solid 1px #d8d8d8;
}
.gj {
  color: #000;
  font-size: 14px;
}
</style>
