<template>
  <div class="hello">
    <button @click="sendRequest()">发送测试请求</button>
    <h1>hello</h1>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'hello',
  data () {
    return {
    }
  },
  methods: {
    sendRequest: () => {
      axios({
        url: '/api/java/Floor/GetAll',
        method: 'post',
        data: {
          hotelId: 6
        },
        headers: {
          'token': 'aaa',
          'Content-Type': 'application/json;charset=UTF-8'
        }
      })
        .then(function (res) {
          console.log(res)
        }, function (error) {
          console.log(error)
        })
    }
  },
  mounted: function () {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
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
