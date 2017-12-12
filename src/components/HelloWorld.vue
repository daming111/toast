<template>
  <div class="hello">
    <div class="mark" v-show="isMarkShow"></div>
    <div class="content">
      <div @click="isShow1=!isShow1;isMarkShow=!isMarkShow">打开 alert 提示框</div>
      <div @click="isShow2=!isShow2;isMarkShow=!isMarkShow">打开 confirm 提示框</div>
      <div @click="isShow3=!isShow3;isMarkShow=!isMarkShow">打开 prompt 提示框</div>
    </div>
    <div class="toast toast1" v-show="isShow1">
      <div class="hint">提示</div>
      <div class="succeed">操作成功!</div>
      <div class="confirm" @click="isShow1=!isShow1;isMarkShow=!isMarkShow">确定</div>
    </div>
    <div class="toast toast2" v-show="isShow2">
      <div class="hint">提示</div>
      <div class="succeed">确定执行此操作?</div>
      <div class="bottom">
        <span class="cancel" @click="isShow2=!isShow2;isMarkShow=!isMarkShow">取消</span>
        <span @click="isShow2=!isShow2;isMarkShow=!isMarkShow">确定</span>
      </div>
    </div>
    <div class="toast toast3" v-show="isShow3">
      <div class="hint">请输入姓名</div>
      <input type="text" class="input" v-model="text">
      <div class="bottom">
        <span class="cancel" @click="isShow3=!isShow3;isMarkShow=!isMarkShow">取消</span>
        <span @click="isShow3=!isShow3;isShow4=!isShow4">确定</span>
      </div>
    </div>
    <div class="toast toast4" v-show="isShow4">
      <div class="hint">输入成功</div>
      <div class="succeed">你的名字是 {{text}}</div>
      <div class="confirm" @click="isShow4=!isShow4;isMarkShow=!isMarkShow;text=''">确定</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      isMarkShow:false,
      isShow1:false,
      isShow2:false,
      isShow3:false,
      isShow4:false,
      text:""
    }
  },
  methods:{
  
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .content{
    width: 85%;
    position: fixed;
    left: 24px;
    top:50%;
    margin-top: -100px;
  }
  .content div{
    height: 35px;
    text-align: center;
    font-size: 18px;
    color: #666;
    background:#eee;
    margin-top:30px;
    line-height: 35px; 
    border: 1px solid #ccc;
    border-radius:5px; 
  }
  .mark{
    height:100%;
    width: 100%;
    position: fixed;
    background: #000;
    z-index: 98;
    top: 0;
    opacity: .6;
  }
  .toast{
    width: 85%;
    margin: 0 auto;
    position: fixed;
    left: 24px;
    top:50%;
    margin-top: -67px; 
    z-index: 99;
    background: #fff;
    border-radius: 5px;
  }
  .toast div{
    text-align: center;
    padding: 10px 0;
  }
  .hint{
    font-size: 16px;
    font-weight: 900;
  }
  .succeed{
    font-size: 16px;
    color: #aaa;
  }
  .confirm,.bottom{
    color: #26a2ff;
    border-top: 1px solid #ccc;
    margin-top: 10px;
  }
  .bottom span{
    display: inline-block;
    width: 48%;
  }
  .cancel{
    color:#333;
    border-right: 1px solid #ccc;
  }
  .input{
    height: 20px;
    border:2px solid #eee;
    width: 80%;
    margin:10px 0 20px 20px;
  }
</style>
