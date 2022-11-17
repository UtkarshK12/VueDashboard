<template>
    <Suspense><DashboardHeader></DashboardHeader></Suspense>
    <Suspense><ErrorLogList></ErrorLogList></Suspense>
</template>

<script setup>
import DashboardHeader from './DashboardHeader.vue'
import ErrorLogList from './ClassErrorList.vue';
</script>