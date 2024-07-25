<template>
    <div class="login-component-wapper">
        <a-form class="login-component" :model="form" @submit="ClickHandler">
            <div class="title">登录</div>
            <div class="login-form">
                <a-form-item field="username" label="用户名">
                    <a-input v-model="form.username" placeholder="请输入用户名">
                        <template #prefix>
                            <icon-user />
                        </template>
                    </a-input>
                </a-form-item>
                <a-form-item field="password" label="密码">
                    <a-input-password v-model="form.password" placeholder="请输入密码">
                        <template #prefix>
                            <icon-lock />
                        </template>
                    </a-input-password>
                </a-form-item>
                <a-form-item field="is_remember">
                    <a-checkbox v-model="form.is_remember">
                        记住我
                    </a-checkbox>
                </a-form-item>
            </div>
            <div class="submit-buttom">
                <a-button type="primary" html-type="submit" :loading="isLoading" @click="LoadingHandler" auto-label-width>
                    submit
                </a-button>
            </div>
        </a-form>
    </div>
</template>

<script setup>
    import { reactive } from "vue";
    import { ref } from "vue";

    const isLoading=ref(false)

    const form = reactive({
        username: '',
        password: '',
        is_remember: false,
    });

    const ClickHandler = (data) => {
        console.log(data);
    };

    const LoadingHandler = () => {
        isLoading.value = !isLoading.value
    }
</script>

<style scoped>
    .title{
        font-size: 30px;
        color: var(--color-neutral-8);
        padding-top: 15px;
        margin: auto;
        margin-bottom: 25px;
    }

    .login-component-wapper{
        width: 100%;
        height: 100%;
        display: flex;
        background: #C6FFDD;  /* fallback for old browsers */
        background: -webkit-linear-gradient(to right, #f7797d, #FBD786, #C6FFDD);  /* Chrome 10-25, Safari 5.1-6 */
        background: linear-gradient(to right, #f7797d, #FBD786, #C6FFDD); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    }
    
    .login-component {
        height: 300px;
        width: 500px;
        margin: auto;
        border-radius: 10px;
        background-color: #FFF;
        border: solid 1px var(--color-neutral-3);
    }
   
    .arco-btn-primary, .arco-btn-primary[type="button"], .arco-btn-primary[type="submit"] {
        color: #fff;
        border-radius: 10px;
        background-color: #7b219f;
        box-shadow: inset 6px -6px 26px #5d1979,
                    inset -6px 6px 26px #9929c5;
        height: 40px;
        width: 350px;
        border: 0px;
        padding: 0px;
        margin: 0px;
    }

    .submit-buttom {
        width: 350px;
        margin: auto;
    }

    .login-form {
        width: 350px;
        height: 130px;
        margin: auto;
        margin-bottom: 0px;
        margin-top: 0px;
    }
</style>