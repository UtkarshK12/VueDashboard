<script setup>
import TimeClock from './components/TimeClock.vue'
import {ref, computed} from 'vue'
import StatDashboard from './components/TestPassComponent.vue'
import Dashboardheader from './components/DashboardHeader.vue'
import TestPassComponent from './components/TestPassComponent.vue';
import LogsStatsVue from './components/LogsStats.vue';
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
</div>
</template>

<style>
.MainPage{
    width:auto;
    flex-direction: row;
    background-color:  white;
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


