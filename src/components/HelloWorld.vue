<template>
  <div></div>
</template>

<script>
import axios from "axios";
export default {
  name: "Incidents",
  props: {
    msg: String,
  },
  data() {
    return {
      incidents: null,
    };
  },
  mounted() {
    axios.get("https://thinkst-frontend-resources.s3-eu-west-1.amazonaws.com/incidents/data.json").then((response) => {
      console.log(response.data);
      console.table(response.data.alerts);
      console.table(response.data.device_list);
    });
  },
};
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
</style>
