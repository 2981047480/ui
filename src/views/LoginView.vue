<template>
    <div class="login-component-wapper">
        <a-form class="login-component" :model="form" @submit="ClickHandler">
            <div class="title">登录</div>
            <div>
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
            <a-button class="submit-button" type="primary" html-type="submit" :loading="isLoading" @click="LoadingHandler" auto-label-width>
                submit
            </a-button>
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
        margin: auto;
        margin-bottom: 25px;
    }

    .login-component-wapper{
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.594);
    }
    
    .login-component{
        height: 300px;
        width: 500px;
        margin: auto;
        background-color: #FFF;
    }
   
    .arco-btn-primary, .arco-btn-primary[type="button"], .arco-btn-primary[type="submit"] {
        color: #fff;
        background-color: rgb(165, 18, 165);
        height: 40px;
        border: 1px solid transparent;
        margin: 3px;
    }
    
    .arco-input-wrapper .arco-input {
        width: 100%;
        padding-right: 10;
        padding-left: 0;
        color: inherit;
        line-height: 1.5715;
        background: none;
        border: none;
        border-radius: 0;
        outline: none;
        cursor: inherit;
        -webkit-appearance: none;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    }
</style>