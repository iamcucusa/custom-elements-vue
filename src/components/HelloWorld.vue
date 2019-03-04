<template>
  <div class="angular">
    <zoom-button :raetId="largeButton" :type="button"></zoom-button>
    <!--<zoom-button v-on:countChange="handleCountChange"></zoom-button>-->
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

.angular{
  border-style: solid;
  border-color: #99050a;
  margin: 30px;
  padding-bottom: 20px;
}
</style>
