<template>
    <div class="container">
        <h1>{{title}}</h1>
        <hr>
        <br>
        <input type="text" name="target" class="get-target" v-model="get_target" placeholder="target html">
        <button v-on:click="doGET">execute GET</button>
        <p>{{result}}</p>
    </div>
</template>

<script>
const axios = require('axios');
let url = "http://localhost:8080"

export default {
    data: function() {
        return {
            title: 'GET page',
            get_target: '',
            result: '',
        };
    }, 
    asyncData: async function(context) {
        url = context.query.target;
        let get_result  = await axios.get(url);
        return {result: get_result.data}
        //return {result: url}
    },
    methods: {
        doGET:function(event) {
            url = this.get_target;
            axios.get(url).then((res) => {
                this.result = res.data;
            });
        },
    },
}
</script>

<style>
.container {
  padding: 5px 10px;
}

h1 {
  font-size: 60pt;
  color: #345980;
}
</style>