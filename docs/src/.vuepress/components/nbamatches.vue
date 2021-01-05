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
    <td style="padding:5px 70px">{{i.ATS.toFixed(2)}}</td>
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
const url = 'https://storage.googleapis.com/nbamodel-223111.appspot.com/data.json'
axios.get(url, {
    responseType: 'text',
    transformResponse: data => data,
}).then(response => {
    this.items = response.data.split('\n').filter(Boolean).map(item => JSON.parse(item))
});

  }
}
</script>
