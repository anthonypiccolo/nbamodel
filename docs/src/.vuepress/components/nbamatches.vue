<template>
  <table>
  <tr style="background-color:DarkSlateGrey;text-align:center;color:white">
    <th style="padding: 5px 70px">Home</th>
    <th style="padding: 5px 70px">Road</th> 
    <th style="padding: 5px 70px">Home ATS</th>
  </tr>
  <tr v-for="i in items" style="text-align:center;margin: 30px">
    <td style="padding:5px 70px">{{i.Home_Neutral}}</td>
    <td style="padding:5px 70px">{{i.Visitor_Neutral}}</td>
    <td style="padding:5px 70px">{{i.ATS}}</td>
  </tr>
</table>
</template>

<style scoped>
table.center {
  margin-left:auto; 
  margin-right:auto;
}
</style>

<script>
import axios from 'axios';
export default {
  name: "get-request",
  data () {
      return {
          items: [],
      };
  },
  created() {
    // Simple GET request using axios
    axios.get("https://firebasestorage.googleapis.com/v0/b/nbamodel-223111.appspot.com/o/data.json?alt=media&token=79253355-fbeb-4939-8686-c1a30bcb791c")
      .then(response => this.items = response.data);

  }
}
</script>
