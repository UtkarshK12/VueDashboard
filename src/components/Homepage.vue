

<script setup>


import TimeClock from './TimeClock.vue'
import {ref, computed} from 'vue'
import StatDashboard from './TestPassComponent.vue'
import Dashboardheader from './DashboardHeader.vue'
import TestPassComponent from './TestPassComponent.vue';
import LogsStatsVue from './LogsStats.vue';
import ErrorClassList from './ErrorClassList.vue';
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
<Suspense><ErrorClassList></ErrorClassList></Suspense>
</div>
</template>

<style scoped>
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


