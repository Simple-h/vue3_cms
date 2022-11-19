<template>
<div class="login">
  <div class="login-body">
    <div class="login-header">
      <h3 class="title">用户登录</h3>
    </div>
    <div class="login-center">
        <el-form :model="loginForm">
          <el-form-item label="账号">
            <el-icon :size="20">
              <UserFilled />
            </el-icon>
            <el-input v-model="loginForm.name" />
          </el-form-item>
          <el-form-item label="密码">
            <el-icon :size="20">
              <Lock />
            </el-icon>
            <el-input v-model="loginForm.password" show-password/>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="onSubmit">登录</el-button>
            <el-button >注册</el-button>
          </el-form-item>
       </el-form>
    </div>
  </div>
</div>
</template>

<script setup lang="ts">
    import { reactive } from "vue";
    import { UserFilled , Lock } from "@element-plus/icons-vue";
    const loginForm = reactive({
      name: '',
      password:'',
    })
    const onSubmit = () => {
      console.log('submit!')
    }

</script>


<style lang="scss">
html{
  width: 100%;
  height: 100%;
  body{
    background-color: #ccc;
    width: 100%;
    height: 100%;
    margin: 0;
  #app{
    position: relative;
    width: 100%;
    height: 100%;
    .login{
      background-color: #fff;
      width: 500px;
      height: 300px;
      position: absolute;
      top: 45%;
      left: 50%;
      margin-left: -250px;
      margin-top: -150px;
      .login-body{
        height: 100%;
        margin-top: -20px;
        .login-header{
          height: 80px;
          background-color: aqua;
          line-height: 80px;
          text-align: center;
          .title{
            height: 80px;
            line-height: 80px;
            font-size: 30px;
            margin: 0;
          }
        }
        .login-center{
          margin-top: 20px;
          .el-form{
            height: 221px;
            .el-form-item{
              padding: 0 60px;
              // padding-right: 100px;
              position: relative;
              .el-form-item__label{
                position: absolute;
                top: 19px;
              }
              .el-form-item__content{
                  padding-left: 50px;
                  position: relative;
                  .el-icon{
                    position: absolute;
                    top: 24px;
                    left: 58px;
                    z-index: 99;
                  }
                  .el-input__password{

                    z-index: 99;
                    svg{
                      position: absolute;
                    top: -15px;
                    right: -240px;
                    
                    }
                  }
                  .el-input{
                    margin-top: 19px;
                    .el-input__inner{
                      padding-left: 25px;
                    }
                  }
                  .el-button{
                    width: 159px;
                    height: 40px;
                    margin-top: 10px;
                    float: left;
                  }
                }
            }

          }
        }
      }
    }
  }
}
}

</style>