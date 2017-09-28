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
        <a href="#" class="current-ticker"></a>
        <a href="#" class="next-ticker"></a>
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
import $ from 'jquery'
export default {
  name: 'app',
  data () {
    return {
      tickers: [
        'Lorem ipsum dolor sit amet, consectetur adipisicing elit.',
        'Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
        'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris.',
        'Nisi ut aliquip ex ea commodo consequat.',
        'Duis aute irure dolor in reprehenderit in voluptate velit esse.'
      ],
      currentTickerIndex: 0
    }
  },
  mounted () {
    $('.current-ticker').text(this.tickers[this.currentTickerIndex])
    setInterval(() => {
      const current = $('.current-ticker').first()
      const next = $('.next-ticker').first()
      this.currentTickerIndex++
      if (this.currentTickerIndex >= this.tickers.length) {
        this.currentTickerIndex = 0
      }
      next.text(this.tickers[this.currentTickerIndex])
      next.css({top: 0, 'z-index': 200})
      current.css({top: 36, 'z-index': 100})

      setTimeout(() => {
        next.removeClass('next-ticker').addClass('current-ticker')
        current.removeClass('current-ticker').addClass('next-ticker')
      }, 500)
    }, 2000)
  }
}
</script>