<script setup>
import TimeClock from './components/TimeClock.vue'
import {ref, computed} from 'vue'
import StatDashboard from './components/TestPassComponent.vue'
import Dashboardheader from './components/DashboardHeader.vue'
import TestPassComponent from './components/TestPassComponent.vue';
const b= computed(()=>{
})

</script>
<template>
<Dashboardheader></Dashboardheader><br>
<Suspense><TimeClock></TimeClock></Suspense>
<Suspense><TestPassComponent></TestPassComponent></Suspense>
</template>


