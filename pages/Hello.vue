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
              <nuxt-link to="/profile/">
                Profile
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
/* @import '../assets/index.css'; */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
}
body {
  background-color: lightslategray;
  background: rgb(176, 222, 201);
  background: linear-gradient(
    280deg,
    rgba(176, 222, 201, 1) 0%,
    rgba(65, 69, 103, 1) 90%
  );
}
.container {
  max-width: 1400px;
  margin: 0 auto;
}

.header-top {
  padding: 2rem 0;
  border-bottom: 1px solid rgb(151, 151, 146);
  padding-bottom: 2rem;
}
.header-top h1 {
  color: rgb(92, 92, 92);
}

ul.menu {
  margin-top: 1rem;
  display: flex;
  font-size: 20px;
  list-style: none; /* ลบbullet */
}
ul.menu li {
  margin-right: 2rem;
}
ul.menu a {
  color: rgb(0, 0, 0);
  text-decoration: none;
  transition: 0.3s;
  padding-bottom: 5px;
  border-bottom: 2px solid transparent;
}
ul.menu a:hover {
  color: rgb(92, 92, 92);
  border-bottom: 2px solid rgb(190, 189, 126);
}

.section-grid {
  border-bottom: 1px solid rgb(151, 151, 146);
  padding-bottom: 2rem;
  margin: 3rem 0 3rem 0;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 1rem;
}
.section-image img {
  box-shadow: black;
  box-shadow: 5px 5px 5px rgb(54, 54, 54);
  -moz-border-radius: 25px;
  -webkit-border-radius: 25px;
  border-radius: 15px;
  width: 100%;
  height: 100%;
}

.section-item {
  font-size: 16px;
}
.section-item a {
  text-decoration: none;
}
.section-item:hover {
  transform: translateY(-5px) translateZ(0);
}

.section-info {
  color: rgb(92, 92, 92);
  margin-top: 1rem;
  margin: 1rem;
}
.section-info h5 {
  font-size: 18px;
}

footer {
  margin-top: 1rem;
}
.footer-grid {
  padding: 2rem;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  justify-items: center;
}
.footer-item {
  color: rgb(92, 92, 92);
}
.footer-item p {
  display: flex;
  margin-top: 1rem;
  font-size: 16px;
}
ul.foot {
  margin-top: 1rem;
  display: flex;
  list-style: none; /* ลบbullet */
}
ul.foot li {
  margin-right: 1rem;
}

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
