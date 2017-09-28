<template>
  <div class="container">
    <div id="app">
    <header>
      <div class="row">
        <div class="col-md-4">
          <a href="" class="logo">
            <img src="./assets/logo-small.png" alt="logo">
            <h1>Selfiejobs</h1>
          </a>
        </div>
        <div class="col-md-8">
          <img src="./assets/header-annons.jpg" class="img-responsive" alt="">
        </div>
      </div>
    </header>
    <nav class="navbar navbar-inverse">
      <div class="collapse navbar-collapse">
        <ul class="nav navbar-nav">
          <li class="active"><a href="#">live</a></li>
          <li><a href="#">Jobbsökare</a></li>
          <li><a href="#">Annonser</a></li>
          <li class="dropdown">
            <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Hjälp <span class="caret"></span></a>
            <ul class="dropdown-menu">
              <li><a href="#">Priser</a></li>
              <li><a href="#">Om oss</a></li>
              <li><a href="#">Investerare</a></li>
              <li><a href="#">Jobs@Selfiejobs</a></li>
              <li><a href="#">Media</a></li>
            </ul>
          </li>
        </ul>
      </div>
    </nav>
    <div class="sub-header">
      <div class="ticker-title">news ticker</div>
      <div class="ticker-content">
        <ul>
          <li v-for="item in tickers" :key="item">
            <a href="#">{{ item }}</a>
          </li>
        </ul>
      </div>
    </div>
    <div id="main">
      <router-view></router-view>
    </div>
    </div>
  </div>
</template>
<script>
require('../node_modules/jquery/dist/jquery.min.js')
require('../node_modules/bootstrap-sass/assets/javascripts/bootstrap.min.js')
require('../node_modules/bootstrap-sass/assets/stylesheets/_bootstrap.scss')
require('./assets/sass/app.scss')
export default {
  name: 'app',
  data () {
    return {
      tickers: [
        'ticker 1',
        'ticker 2',
        'ticker 3',
        'ticker 4'
      ]
    }
  },
  mounted () {
    console.log('abc')
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
