<template>
  <div class="hello" style="text-align: left;">
      <h1>Welcome to Tstrap.</h1>
      <p>
          This is a straightforward app shell designed to provide an easy way to
          quickly start work on an app made with Vue / Semantic-UI / Electron (coming soon).
      </p>
      <p>Ideally you should be able to be up and running with the following simple steps:</p>
      <ol class="ui list">
          <li>Clone the Tstrap repo</li>
          <li>Adjust <code>Application.js</code> to suit your needs (it's intended to be self-explanatory)</li>
          <li>Create <code>.vue</code> components in <code>src/components</code> and add them to <code>Application.js</code>.</li>
      </ol>
      <h2>Vue links</h2>
      <s_table>
      <tbody>
          <tr>
              <td><a href="https://vuejs.org" target="_blank">Core Vue docs</a></td>
          </tr>
          <tr>
              <td><a href="https://forum.vuejs.org" target="_blank">Vue Forum</a></td>
          </tr>
          <tr>
              <td><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></td>
          </tr>
          <tr>
              <td><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></td>
          </tr>
          <tr>
              <td><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for this template</a></td>
          </tr>
      </tbody>
      </s_table>
      <h2>Vue ecosystem</h2>
      <s_table>
      <tbody>
          <tr>
              <td><a href="http://router.vuejs.org/" target="_blank">vue-router</a></td>
          </tr>
          <tr>
              <td><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></td>
          </tr>
          <tr>
              <td><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></td>
          </tr>
          <tr>
              <td><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></td>
          </tr>
          
      </tbody>
      </s_table>
    <h1>{{ message }}</h1>
  </div>
</template>

<script>

import { Looper } from '../tstrap/Util';

let $m = {
    /* Model */
    /* Declare all your model attribs in here, even if 
    you're not using them yet, or Vue will get cross */
    message: ''
};
let $s = null;  /* Vuex store placeholder */
let $loops = [];

export default {
    name: 'HelloWorld',
    data: () => $m,
    
    beforeCreate () {
        $m.message = 'Now get started making something cool!! :)'
    },
    
    mounted () {
        /* Populate initial values, initiate fetches, etc. */
        /* Show a tick every 5s */
        $loops.push(
            new Looper(nowt => console.log('tick')).run(5000)
        );
    },
    
    beforeDestroy () {
        /* Tidyup */
        Looper.stopAll($loops);
    }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- If you want to add CSS across the whole app, scope it to AppContainer -->
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
