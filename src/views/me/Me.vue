<template>
  <div>
    <el-row type="flex" justify="space-around">
      <el-col :span="6">
        <div class="one"><h1 class="el-icon-eleme">首页</h1></div>
      </el-col>

      <el-col :span="6">
        <div class="one"><h1 class="el-icon-s-operation">分类</h1></div>
      </el-col>

      <el-col :span="6">
        <div class="one"><h1 class="el-icon-user-solid">个人中心</h1></div>
      </el-col>
    </el-row>

    <el-row>
      <el-col :span="6">
        <div class="two">
          <el-row>
            <el-col :span="8"><h4>标题1</h4></el-col>
            <el-col :span="8"><h4>标题2</h4></el-col>
            <el-col :span="8"><h4>标题3</h4></el-col>
          </el-row>

          <el-row>
            <el-col :span="6">
              <span>ha</span>
            </el-col>

            <el-col :span="6">
              <span>ha</span>
            </el-col>

            <el-col :span="6">
              <span>ha</span>
            </el-col>

            <el-col :span="6">
              <span>a</span>
            </el-col>
          </el-row>
          <el-row :gutter="10">
            <el-col :span="12">
              <el-input
                v-model="message"
                placeholder="请输入..."
                clearable
                prefix-icon="el-icon-user-solid"
              ></el-input>
            </el-col>
            <el-col :span="12">
              <el-input placeholder="" disabled></el-input>
            </el-col>
          </el-row>

          <el-row>
            <el-col :span="18" :offset="3">
              <el-input
                v-model="password"
                placeholder="请输入密码..."
                show-password
                prefix-icon="el-icon-star-on"
              ></el-input>
            </el-col>
          </el-row>
        </div>
      </el-col>

      <el-col :span="6">
        <div class="two">
          22
        </div>
      </el-col>

      <el-col :span="6">
        <div class="two">33</div>
      </el-col>

      <el-col :span="6">
        <div class="two">44</div>
      </el-col>
    </el-row>

    <el-row>
      <el-col :span="24">
        <div class="foot">foot</div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "Me",
  data() {
    return {
      message: "",
      password: ""
    };
  }
};
</script>

<style scoped>
.one {
  background-color: #bfa;
  text-align: center;
  height: 100px;
  line-height: 100px;
}

.two {
  /* width: 98%; */
  height: 300px;
  background-color: #e6a23c;
}

h1 {
  margin: 0;
  padding: 0;
  text-align: center;
}

.foot {
  width: 100%;
  height: 100px;
  background-color: #bfe;
  line-height: 100px;
  text-align: center;
}

.three {
  width: 98%;
  background-color: #67c23a;
  height: 100px;
  margin: 5px 0;
}
</style>
