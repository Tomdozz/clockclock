<template>
  <div class="main">
    <Clock
      hour="21"
      minute="55"
      style="position: absolute; top: 0%; left:0%;"
      uid="1"
    />
    <Clock
      hour="21"
      minute="15"
      style="position: absolute; top: 0%; left:50%;"
      uid="2"
    />
    <Clock
      hour="21"
      minute="15"
      style="position: absolute; top: 0%; left:25%;"
    />
  </div>
</template>

<script>
import Clock from "@/components/Clock.vue";

export default {
  name: "HelloWorld",
  components: {
    Clock
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
</style>
