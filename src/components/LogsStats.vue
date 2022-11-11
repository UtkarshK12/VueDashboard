<template>
<div class="LogStats">

        <div class="units">
        <div class="text"><h6>Test Coverage</h6></div>
        <div class="container">
        <div class="test coverage">{{coverage}}</div>
        </div>
        </div>
        
       
        <div class="units">
        <div class="text"><h6>Passed Tests</h6></div>
        <div class="container">
        <div class="test passed">{{passed}}</div>
        </div>
        </div>

        <div class="units">
        <div class="text"><h6>Failed Tests</h6></div>
        <div class="container">
        <div class="test failed">{{failed}}</div>
        </div>
        </div>

        <div class="units">
        <div class="text"><h6>Tests Skipped</h6></div>
        <div class="container">
        <div class="test skipped">{{skipped}}</div>
        </div>
        </div>

</div>
    
</template>
<script setup>
    
  import {ref} from 'vue';

 let passed=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    passed.value = data[88]['id']; // this will be a string
  });

  passed.value= passed.value+'%';


  let coverage=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    coverage.value = data[65]['id']; // this will be a string
  });

  coverage.value= coverage.value+'%';

  let failed=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    failed.value = data[10]['id']; // this will be a string
  });

  failed.value= failed.value+'%';

  let skipped=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    skipped.value = data[80]['id']; // this will be a string
  });

  skipped.value= skipped.value+'%';

  let defects=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    defects.value = data[80]['id']; // this will be a string
  });

  defects.value= passed.value+'%';

</script>


<style scoped>
.LogStats{
    align-items: center;
    width: 600px;
  display: flex;
  height: 300px;
  box-sizing: border-box;
  background-color: lightblue;
  flex-direction: column;
  border-radius: 30px;
  justify-content:space-between;
}
.units{
    display:flex;
    flex-direction: row;
    width: 90%;
    align-items:center;
    font-family: sans-serif;
    font-style: italic;
}

.text{
   width: 80px;
}

p {
        font-size: 15px;
    }
  
    .container {
        background-color: white;
        width: 20%;
        padding: 1%;
        height: 15px;
        border-radius: 15px;
        flex: 1 1 0
      
    }
  
    .test {
        background-color: darkcyan;
        color: white;
        height: 15px;
        text-align: right;
        font-size: 15px;
        border-radius: 15px;
        
    }
  
    .coverage{
        width: v-bind(coverage);
        background-color: darkcyan;
    }
    
    .passed{
        background-color: green;
        width: v-bind(passed);
    }

    .failed{
        background-color: lightcoral;
        width: v-bind(failed);
    }

    .skipped{
        background-color: yellowgreen;
        width: v-bind(skipped);
    }

</style>