<template>
  <div id="app">
    <header id="header">
      <h1>GROUPOMANIA SOCIAL NETWORK <i></i></h1> 
    </header>
    <div id="nav">
      <router-link to="/forum"> Forum |</router-link>
      <router-link to="/profile"> Profile</router-link>
      <button v-if="isLoggedIn" @click.stop.prevent="disconnect">Déconnection</button>     
    </div>
    <router-view/>
  </div>
</template>

<script>
import Store from './store'
import {mapState} from 'vuex'
export default {
  name: 'App',
  computed:{
    ...mapState(['isLoggedIn'])
  },
  methods: {
    disconnect(){
      Store.dispatch('disconnect')
    }
  }
}
</script>

<style lang="scss">
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}

body {
  background-image: url("../images/icon.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  min-height: 100%;
  
}
#header{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100px;
  font-size: 2em;
  font-weight: bold;
}
#nav {
  position: relative;
  padding: 30px;
  
  button{
    position: absolute;
    right: 0;
    border: none;
    background-color: black;
    color: white;
  }
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
