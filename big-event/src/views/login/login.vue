<template>
    <div class="login">
        <div class="login-title">
            <img src="@/assets/images/login_title.png" alt="">
        </div>
        <el-card class="login-card">
            <div slot="header">
                <span>后台管理系统注册</span>
            </div>
            <div class="form">
                <el-form status-icon :rules="rules" label-width="100px">
                    <el-form-item label="用户名" prop="username">
                        <el-input v-model="form.username" autocomplete="off"></el-input>
                    </el-form-item>
                    <el-form-item label="密码" prop="password">
                        <el-input type="password" v-model="form.password" autocomplete="off"></el-input>
                    </el-form-item>
                    <el-form-item class="login-btn">
                        <el-button type="primary" style="margin-right: 20px;">登 录</el-button>
                        <el-button>取 消</el-button>
                    </el-form-item>
                </el-form>
            </div>
        </el-card>
    </div>
</template>

<script>
export default {
    name: "LoginPage",
    data() {
        return {
            form: {
                username: '',
                password: ''
            },
            rules: {
                username: [
                    { required: true, message: '请输入用户名', trigger: 'blur' },
                    { min: 3, max: 12, message: '长度在 3 到 12 个字符', trigger: 'blur' }
                ],
                password: [
                    { required: true, message: '请输入密码', trigger: 'blur' },
                    { min: 6, max: 12, message: '长度在 6 到 12 个字符', trigger: 'blur' }
                ]
            }
        }
    },
}
</script>
<style lang="less" scoped>
.login {
    position: relative;
    width: 100%;
    height: 100vh;
    background: url('@/assets/images/login_bg.jpg') no-repeat center / cover;

    .login-title {
        position: absolute;
        left: 50%;
        top: 20%;
        transform: translate(-50%);
        z-index: 999;
    }

    .login-card {
        position: absolute;
        width: 400px;
        margin: 0px auto;
        padding: 20px;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        text-align: center;

        .form {
            transform: translate(-10%);
        }

        .login-btn {
            text-align: center;
        }
    }
}
</style>