<template>
    <div class="head">
        <h2>&nbsp Error Log</h2>
            <!-- <form @submit.prevent="searchfilter">
            <input v-model="searchText">
            <button>Search</button>    
            </form> -->
    </div>
    <br>
    <div class="errorList">

        <div v-for="bees in b">
        
            <div class="errorListBox">
               
                <div class="space0">
                </div>
                <div class="noOfErrors">
                    <h3>{{bees['id']}} </h3>    
                </div>
                <div class="space1">
              </div>

                <div class="errorClass">
                    <h3><router-link to="/classErrorList/">Error Class Name</router-link> </h3>    
                </div>
                <div class="space2">
                </div>
                <div class="errorTimestamp">
                    <h3>{{bees['id']}}/{{bees['id']}}/{{bees['id']}}{{bees['id']}}{{bees['id']}} </h3>    
                </div>
                <div class="space3">
                </div>
                <div class="percentageCompletion">
                    <h3>{{bees['id']}} </h3>    
                </div>
            </div>
            <br>
        </div>

    </div>
    
    
</template>
<script setup>
import {ref} from 'vue';
import LogsStats from './LogsStats.vue';

let searchText=ref();

let b=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    b.value = data; 
  });

</script>
<style scoped>
    h2{
        
        color: white;
        font-size: large ;
        font-family: sans-serif;
    }
    .head{
        box-sizing: border-box;
        background-color: darkcyan;
        padding: 0.3%;
        border-radius: 30px;
    }
    .errorListBox{
        font-family: sans-serif;
        box-sizing: border-box;
        display: flex;
        flex-direction: row;
        background-color: lightblue;
        border-radius: 30px;
        align-items: center;
        font-size: small;
    }
    .space0{
        width: 5%;
    }
    .space1{
        width: 10%;
    }

    .space2{
        width: 55%;
    }
    .space3{
        width: 7%;
    }

    .noOfErrors{
        background-color: lightsteelblue;
        box-sizing: border-box;
        height: 50px;
        width:50px;
        align-items: center;
        text-align: center;
        border-radius: 10px;
    }
</style>