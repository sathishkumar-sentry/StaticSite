<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    let recaptchaScript = document.createElement('script');
    recaptchaScript.setAttribute('src', 'https://unpkg.com/upvote-page-helper/dist/upvote-page-helper.umd.js');
    document.head.appendChild(recaptchaScript);
    !function(){function e(e,t){"Upvoted"===t?e.classList.add("voted"):e.classList.remove("voted")}!function(){try{var t=document.createElement("span");t.textContent="△";var o=document.createElement("div");o.appendChild(t);var n=document.createElement("span");o.appendChild(n),o.classList.add("vote");var r=new window.upvote("2d7f29f3-c7fb-4a03-bf51-a461984b2794");Promise.resolve(r.getVotes()).then(function(t){n.textContent=t.Votes,e(o,t.Status),o.addEventListener("click",function(t){try{return Promise.resolve(r.toggleVote()).then(function(t){n.textContent=t.Votes,e(o,t.Status)})}catch(e){return Promise.reject(e)}});var a=document.createElement("style");a.textContent=".vote{display:flex;flex-direction:column;justify-content:center;align-items:center;border-radius:50%;padding:10px;box-shadow:rgba(0,0,0,.1) 0 9.85px 40px 0;height:40px;width:40px;font-family:Arial,Helvetica,sans-serif;font-size:16px;cursor:pointer;user-select:none;border:1px solid transparent;position:absolute;left:15px;bottom:15px;transition:250ms ease-in all}.vote:hover{box-shadow:rgba(0,0,0,.2) 0 9.85px 40px 0}.vote.voted{color:#04befe;border-color:#04befe}",document.head.append(a),document.body.append(o)})}catch(e){return Promise.reject(e)}}()}();
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
