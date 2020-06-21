<template>
  <div>
    <header>
      <div class="container">
        <div class="header-top">
          <h1>M.2DEV</h1>
          <ul class="menu">
            <li>
              <nuxt-link to="/">
                Today News
              </nuxt-link>
            </li>
            <li>
              <a href="https://github.com/moszie248">
                comming
              </a>
            </li>
            <li>
              <a href="https://github.com/moszie248">
                comming
              </a>
            </li>
            <li>
              <a href="https://github.com/moszie248">
                comming
              </a>
            </li>
            <li>
              <a href="https://github.com/moszie248">
                comming
              </a>
            </li>
          </ul>
        </div>
      </div>
    </header>
    <section>
      <div class="container">
        <!-- <div class="section-title">
          <div class="sec-left">
            <i class="fas fa-chevron-left"></i>
          </div>
          <div class="sec-right"></div>
        </div> -->
        <div class="section-grid">
          <div
            v-for="headline in headlines"
            :key="headline.id"
            class="section-item"
          >
            <a :href="headline.url">
              <div class="section-image">
                <img
                  class="card-img-top"
                  :src="headline.urlToImage"
                  alt="Card image cap"
                />
              </div>
              <div class="section-info">
                <h5>{{ headline.title }}</h5>
                <small>{{ headline.author }}</small>
              </div>
            </a>
          </div>
        </div>
      </div>
    </section>
    <footer>
      <div class="container">
        <div class="footer-grid">
          <div class="footer-item">
            <h2>NewsLetter</h2>
            <p></p>
          </div>
          <div class="footer-item">
            <h2>Information</h2>
            <p>Home</p>
          </div>
          <div class="footer-item">
            <h2>Help</h2>
            <p>Contact us</p>
          </div>
          <div class="footer-item">
            <h2>Contact</h2>
            <ul class="foot">
              <li>Facebok</li>
              <li>Instagram</li>
              <li>Twitter</li>
              <li>Line</li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>
<script src="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css"></script>
<script>
export default {
  async asyncData({ app }) {
    const topHeadlines = await app.$axios.$get(
      'https://newsapi.org/v2/top-headlines?country=us'
    )
    return { headlines: topHeadlines.articles }
  }
}
</script>

<style>
@import '../assets/index.css';
.box-card {
  padding: 10px;
  margin: auto;
  max-width: 30%;
  margin-top: 15px;
}

.box-card:hover {
  transform: translateY(-5px) scale(1.005) translateZ(0);
  box-shadow: 0 24px 36px rgba(0, 0, 0, 0.11),
    0 24px 46px var(--box-shadow-color);
}
</style>
