<template>
<div class="TestPass">
<h3> Passed Tests </h3>
<div class="pie animate" style="--p:{{b}};--c:lightgreen"> 90%</div>


</div>
</template>

<script >
    
  import {ref} from 'vue';
const a = ref();

await fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(function(response) {
    return response.json();
  }).then(function(data) {
    a.value = data['id']; // this will be a string
  });

 const b=ref(100); 
  // await fetch('https://jsonplaceholder.typicode.com/todos/1')
  // .then(function(response) {
  //   return response.json();
  // }).then(function(data) {
  //   b.value = data['id']; // this will be a string
  // });

</script>

<style scoped>


@property --p{
  syntax: '<number>';
  inherits: false;
  initial-value: v-bind("b");
}

.pie {
  --p:80;
  --b:22px;
  --c:darkred;
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