<script setup>
import {RouterView} from "vue-router";
// RouterView는 현재 경로에 해당하는 라우팅 컴포넌트를 자동으로 매핑하고 렌더링해줍니다
// 이를 통해 각 페이지에 대한 컴포넌트를 자동으로 스위칭하게 됩니다. 이 부분이 없으면 페이지 생성x
</script>
<template>
    <RouterView/>
</template>