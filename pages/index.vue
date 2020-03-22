<template>
  <div class="container">
    <h1>{{title}}</h1>
    <hr>
    <router-link to="/get">GET page</router-link>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data: function() {
    return {
      title: 'curl maker',
    };
  },
})
</script>

<style>
.container {
  padding: 5px 10px;
}

h1 {
  font-size: 60pt;
  color: #345980;
}

.links {
  padding-top: 15px;
}
</style>
