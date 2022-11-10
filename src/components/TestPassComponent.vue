<template>
<div class="TestPass">
<h2> Passed Tests </h2>
<div class="pie" style="--c:darkcyan;--b:15px"> {{b}}%</div>
<br>

</div>
</template>

<script setup>
    
  import {ref} from 'vue';

 let b=ref(); 
  await fetch('https://jsonplaceholder.typicode.com/todos')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    b.value = data[89]['id']; // this will be a string
  });

</script>

<style scoped>

.TestPass{
  align-items: center;
  width: 350px;
  display: flex;
  height: 300px;
  box-sizing: border-box;
  background-color: lightblue;
  flex-direction: column;
  justify-content: space-between;
  border-radius: 30px;
  font-family: sans-serif;

}

.TestPass h3{
  align-items: center;
}
/* 
:root{
  --b: 100;
} */

@property --p{
  syntax: '<number>';
  inherits: true;
  initial-value: v-bind(b);
}

.pie {
  --p:v-bind('b');
  --b:22px;
  --c:darkcyan;
  --w:150px;

  width: var(--w);
  aspect-ratio: 1;
  position: relative;
  display: inline-grid;
  margin: 5px;
  place-content: center;
  font-size: 25px;
  font-weight: bold;
  font-family: sans-serif;
}
.pie:before,
.pie:after {
  content: "";
  position: absolute;
  border-radius: 50%;
}
.pie:before {
  inset: 0;
  background:
    radial-gradient(farthest-side,var(--c) 98%,#0000) top/var(--b) var(--b) no-repeat,
    conic-gradient(var(--c) calc(var(--p)*1%),#0000 0);
  -webkit-mask: radial-gradient(farthest-side,#0000 calc(99% - var(--b)),#000 calc(100% - var(--b)));
          mask: radial-gradient(farthest-side,#0000 calc(99% - var(--b)),#000 calc(100% - var(--b)));
}
.pie:after {
  inset: calc(50% - var(--b)/2);
  background: var(--c);
  transform: rotate(calc(var(--p)*3.6deg)) translateY(calc(50% - var(--w)/2));
}
.animate {
  animation: p 1s .5s both;
}
.no-round:before {
  background-size: 0 0, auto;
}
.no-round:after {
  content: none;
}
@keyframes p{
  from{--p:0}
}
</style>