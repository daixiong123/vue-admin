<template>
  <div class="login">
    <div class="button">
      <div @click="tab" data-ind="1" :class="{'active': switchover==1}">登录</div>
      <div @click="tab" data-ind="2" :class="{'active': switchover==2}">注册</div>
    </div>
    <div class="login_" v-if="switchover==1">
      <label>
        <span>账号：</span>
        <div>
          <input placeholder="请输入账号" type="text" v-model="user" />
          <p v-if="ts" class="ts">{{user==""?"账号不能为空!":""}}</p>
        </div>
      </label>
      <label>
        <span>密码：</span>
        <div>
          <input placeholder="请输入密码" type="password" v-model="passw" />
          <p v-if="ts" class="ts">{{passw==""?"密码不能为空!":passw.length<6 ? "密码不能小于六位数":""}}</p>
        </div>
      </label>
      <div>
        <div @click="longin" class="queding">确定</div>
      </div>
    </div>
    <div class="regin" v-else>
      <div>
        <label>
          <span>账号：</span>
          <div>
            <input placeholder="请输入账号" type="text" v-model="user" />
            <p v-if="ts" class="ts">{{user==""?"账号不能为空!":""}}</p>
          </div>
        </label>
        <label>
          <span>密码：</span>
          <div>
            <input placeholder="请输入密码" type="password" v-model="passw" />
            <p v-if="ts" class="ts">{{passw==""?"密码不能为空!":""}}</p>
          </div>
        </label>
        <label>
          <span>再次输入密码：</span>
          <div>
            <input placeholder="请再次输入密码" type="password" v-model="passw_" />
            <p v-if="ts" class="ts">{{passw!=passw_?"密码不一致!":""}}</p>
          </div>
        </label>
        <div @click="regin_" class="zhuce">注册</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      user: "11111",
      passw: "",
      switchover: 1,
      passw_: "",
      ts: false
    };
  },
  methods: {
    tab: function(event) {
      console.log(this);
      console.log(event);
      this.switchover = event.target.dataset.ind;
      this.user = "";
      this.passw = "";
      this.ts = false;
    },
    longin: function() {
      this.ts = true;
    },
    regin_: function() {
      this.ts = true;
      // if (this.passw != this.passw_) {
      //   alert("密码不一致");
      // }
    }
  }
};
</script>
<style lang="scss" scoped>
.login {
  padding-top: 50px;
  width: 800px;
  margin: 0 auto;
}
.ts {
  color: red;
}
label span:first-child {
  width: 120px;
  display: inline-block;
  text-align: right;
}
label div {
  position: relative;
}
label div p {
  position: absolute;
  left: 0;
  bottom: -18px;
  font-size: 12px;
}
.button {
  display: flex;
  justify-content: center;
}
.button div,
.queding,
.zhuce {
  width: 150px;
  line-height: 40px;
  background: #777;
  color: #fff;
  text-align: center;
  border-radius: 2px;
  margin-left: 50px;
  cursor: pointer;
}
.queding,
.zhuce {
  margin: 0 auto;
  background: cornflowerblue;
}
.button .active {
  background: cornflowerblue;
}
.login_ label,
.regin label {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 40px 0;
}
.login_ label input,
.regin label input {
  width: 300px;
  line-height: 30px;
  margin-right: 10px;
}
</style>