

<script setup>


import TimeClock from './TimeClock.vue'
import {ref, computed} from 'vue'
import StatDashboard from './TestPassComponent.vue'
import Dashboardheader from './DashboardHeader.vue'
import TestPassComponent from './TestPassComponent.vue';
import LogsStatsVue from './LogsStats.vue';
import ErrorLogList from './ErrorLogList.vue';
const b= computed(()=>{
})



</script>

<template>
<div class = "MainPage">
<Dashboardheader></Dashboardheader><br>
<div class="UpperStats"><br>
<Suspense><TimeClock></TimeClock></Suspense><br>
<Suspense><TestPassComponent></TestPassComponent></Suspense><br>
<Suspense><LogsStatsVue></LogsStatsVue></Suspense>
</div>
<br>
<Suspense><ErrorLogList></ErrorLogList></Suspense>
</div>
</template>

<style>
.MainPage{
    width:auto;
    flex-direction: row;
    background-color:  whitesmoke;
;
    align-items:stretch
;
}

.UpperStats{
    align-items: stretch;
    display: flex;
    flex-direction: row;
    gap: 20px
}
</style>


