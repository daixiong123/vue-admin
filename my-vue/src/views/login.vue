<template>
  <div class="login">
    <div class="button">
      <div @click="tab" data-ind="1" :class="{'active': switchover==1}">登录</div>
      <div @click="tab" data-ind="2" :class="{'active': switchover==2}">注册</div>
    </div>
    <div class="login_">
      <label>
        <span>账号：</span>
        <input type="text" v-model="user" />
      </label>
      <label>
        <span>密码：</span>
        <input type="password" v-model="passw" />
      </label>
    </div>
    <div>
      <div @click="longin" class="queding">确定</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      user: "11111",
      passw: "",
      switchover: 1
    };
  },
  methods: {
    tab: function(event) {
      console.log(this);
      console.log(event);
      this.switchover = event.target.dataset.ind;
    },
    longin: function() {}
  }
};
</script>
<style lang="scss" scoped>
.login {
  padding-top: 50px;
  width: 800px;
  margin: 0 auto;
}
.button {
  display: flex;
  justify-content: center;
}
.button div,
.queding {
  width: 150px;
  line-height: 40px;
  background: #777;
  color: #fff;
  text-align: center;
  border-radius: 2px;
  margin-left: 50px;
  cursor: pointer;
}
.queding {
  margin: 0 auto;
  background: cornflowerblue;
}
.button .active {
  background: cornflowerblue;
}
.login_ label {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 20px 0;
}
.login_ label input {
  width: 300px;
  line-height: 30px;
}
</style>