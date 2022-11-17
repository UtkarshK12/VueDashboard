<template>
    <Suspense><DashboardHeader></DashboardHeader></Suspense>
    <br>
    <Suspense><ErrorDetails></ErrorDetails></Suspense>
</template>>

<script setup>
import DashboardHeader from './DashboardHeader.vue'
import ErrorDetails from './ErrorDetails.vue'
</script>