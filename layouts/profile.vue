<template>
  <div>
    <!-- <div class="header-top">
      <nav>
        <ul>
          <li>
            <a href="">hellololo</a>
          </li>
          <li>
            <a href="">NICE</a>
          </li>
          <li>
            <a href="">HOTTUT</a>
          </li>
          <li>
            <a href="">OHHH</a>
          </li>
        </ul>
      </nav>
      <button>hello</button>
    </div> -->
    <header class="main_h">
      <div class="row">
        <a class="logo" href="#">M.2DEV</a>

        <div class="mobile-toggle">
          <span></span>
          <span></span>
          <span></span>
        </div>

        <nav>
          <ul>
            <li>
              <nuxt-link to="/">
                Today News
              </nuxt-link>
            </li>
            <li><a href=".sec01111">Section 01</a></li>
            <li><a href=".sec01111">Section 01</a></li>
            <li><a href=".sec02">Section 02</a></li>
            <li><a href=".sec03">Section 03</a></li>
          </ul>
        </nav>
      </div>
      <!-- / row -->
    </header>

    <nuxt />
  </div>
</template>
<script>
import $ from 'jquery'
export default {
  mounted() {
    // Sticky Header
    $(window).scroll(function() {
      if ($(window).scrollTop() > 100) {
        $('.main_h').addClass('sticky')
      } else {
        $('.main_h').removeClass('sticky')
      }
    })

    // Mobile Navigation
    $('.mobile-toggle').click(function() {
      if ($('.main_h').hasClass('open-nav')) {
        $('.main_h').removeClass('open-nav')
      } else {
        $('.main_h').addClass('open-nav')
      }
    })

    $('.main_h li a').click(function() {
      if ($('.main_h').hasClass('open-nav')) {
        $('.navigation').removeClass('open-nav')
        $('.main_h').removeClass('open-nav')
      }
    })

    // navigation scroll lijepo radi materem
    $('nav a').click(function(event) {
      const id = $(this).attr('href')
      const offset = 70
      const target = $(id).offset().top - offset
      $('html, body').animate(
        {
          scrollTop: target
        },
        500
      )
      event.preventDefault()
    })
  }
}
</script>
<style></style>
