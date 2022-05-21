<template>

  <div>

  <el-input v-model="user.username" placeholder="请输入登录用户名"></el-input>
  
  <el-row>
    <el-button type="primary" @click="submit">登录</el-button>
  </el-row>

  </div>

</template>

<script>

export default {
  // name: "addUser",
  data() {
    return {
      user: {
        username: 'zhangsan'
      }
    }
  },
  methods: {
    submit() {
      console.log(this.user.username);
      sessionStorage.setItem("user", JSON.stringify(this.user));
      console.log("登录,存session数据:" + JSON.parse(sessionStorage.getItem("user")).username);
      this.$router.push("/im")
      
    },
  }

}

</script>