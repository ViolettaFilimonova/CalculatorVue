<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div  class="grid ">
      <div class="item current">0</div>
      <div class="item">C</div>
      <div class="item">+/-</div>
      <div class="item">%</div>
      <div class="item operator">/</div>
      <div class="item">7</div>
      <div class="item">8</div>
      <div class="item">9</div>
      <div class="item operator">X</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
      <div class="item operator">-</div>
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item operator">+</div>
      <dic class="zero item">0</dic>
      <dic class="item">.</dic>
      <dic class="item operator">=</dic>
    </div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.grid{
  margin: 60px  auto 0px;
  width: 600px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}
.zero{
  grid-column: 1/3;
}
.item{
  border: 1px solid black;
  padding: 15px;
  background-color: antiquewhite;
  font-size: 20px;
}
.current{
  grid-column: 1/5;
  background-color: #94ccff;
}
.operator{
  background-color: #c88bff;
}
</style>
