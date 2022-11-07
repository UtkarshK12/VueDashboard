<template>
    <div class="clock">
        
    <div class="text"><p>
        Test Duration 
    </p></div>
    
    <div class="Number">
        <h1>
            {{a}}
        </h1>
    <h1>:</h1>
        <h1>
            {{b}}
        </h1>
    </div>

    <div class="Desc">
        <h4>
            hour
        </h4>
        <h4>
            min
        </h4>
    </div>
    </div>
</template>

<script setup>
import {ref} from 'vue';
const a = ref();

await fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    a.value = data['id']; // this will be a string
  });

// a.value = await response.json()["hour"];
const b= ref();

await fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    b.value = data['id']; // this will be a string
  });

</script>

<style scoped>

.clock{
  align-items: center;
  width: 150px;
  display: flex;
  height: 200px;
  box-sizing: border-box;
  background-color: lightblue;
  flex-direction: column;
  justify-content: space-between;
  
}

.Number{
    display: flex;
}
.Desc{
    
    display: flex;
    gap: 10px;
    justify-content: space-between;
    font-family: sans-serif;
    font-size: small;
}
.Number h1 {
  font-weight: normal;
  letter-spacing: .125rem;
  text-transform: uppercase;
}
.Desc h4 {
  font-weight: normal;
  letter-spacing: .125rem;
  text-transform: uppercase;
}


</style>