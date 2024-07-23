<template>
    <a-form class="warpper" :model="form" :style="{width: '400px'}" @submit="ClickHandler">
        <div class="title">登录</div>
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
        <a-button type="primary" html-type="submit" :loading="isLoading" @click="LoadingHandler">
            submit
        </a-button>
    </a-form>
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

<style>
    .title{
        font-size: 30px;
        color: var(--color-neutral-8);
        margin: auto;
        margin-bottom: 25px;
    }

    .warpper{
        margin: auto;
    }
</style>