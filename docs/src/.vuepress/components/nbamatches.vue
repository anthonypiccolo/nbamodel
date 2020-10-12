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
const url = 'https://firebasestorage.googleapis.com/v0/b/nbamodel-223111.appspot.com/o/data.json?alt=media&token=a14b67ec-d567-4179-8df2-207dddf3d505'
axios.get(url, {
    responseType: 'text',
    transformResponse: data => data,
}).then(res => {
    this.items = response.data.split('\n').filter(Boolean).map(item => JSON.parse(item))
});

  }
}
</script>
