<template>
<van-nav-bar
    title="标题"
    left-arrow
    @click-left="onClickLeft"
/>

<div id="content">
 <template v-if="active === 'index'">
    <Index />
 </template>
 <template v-if="active === 'team'">
    <Team />
 </template>
</div>

<van-tabbar v-model="active">
  <van-tabbar-item name="index" icon="home-o">主页</van-tabbar-item>
  <van-tabbar-item name="team" icon="search">队伍</van-tabbar-item>
  <van-tabbar-item name="user" icon="friends-o">个人</van-tabbar-item>
</van-tabbar>

</template>

<!-- 指定setup，那我们在script中定义的变量都会暴露给页面,不用额外return-->
<script setup>

import Index from "../pages/Index.vue";
import Team from "../pages/Team.vue";

import {ref} from "vue";

const onClickLeft = () => alert("左");

const active = ref('index');
</script>