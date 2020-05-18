<template>
  <div>
    <header>
      <div class="container">
        <div class="navbar">
          <nuxt-link to="/" class="logo">
            <img src="../assets/vectors/typo-terradia-white.svg">
          </nuxt-link>
          <nav>
            <ul>
<!--              <li>-->
<!--                <nuxt-link to="/terradia-cest-quoi">À Propos</nuxt-link>-->
<!--              </li>-->
<!--              <li>-->
<!--                <nuxt-link to="/contact">Contact</nuxt-link>-->
<!--              </li>-->
            </ul>
          </nav>
        </div>
      </div>
    </header>
    <nuxt/>
    <footer>
      <img src="../assets/vectors/typo-terradia-white.svg">
      4 Rue du Dôme<br>
      67000 - Strasbourg
      <a href="mailto:" class="link-mail">contact@terradia.eu</a>
      <div class="social-medias">
        <p>Retrouve nous sur les réseaux sociaux</p>
        <a href="https://www.instagram.com/terradiaapp/">
          <fa :icon="['fab', 'instagram']" class="fa-size"/>
        </a>
        <a href="https://www.facebook.com/TerradiaApp/">
          <fa :icon="['fab', 'facebook']" class="fa-size"/>
        </a>
      </div>
      <div class="copyrights">
        &copy; 2020 Terradia - Tous droits réservés.
      </div>
    </footer>
  </div>
</template>

<style lang="scss">

  footer {
    color: white;
    padding-top: 5em !important;
    padding: 1em;
    clip-path: polygon(0 0, 100% 32%, 100% 100%, 0 100%);
    background: linear-gradient(to left, #2BA54C, #5CC04A, #8FDD3D 35%);
    height: 18em;
    display: grid;
    bottom: 0;
    padding-bottom: 0 !important;

    .link-mail {
      color: #ffffff;
      text-decoration: none;
    }

    .fa-size {
      padding: 0.1em;
      font-size: 45px;
      color: white;
    }

    .social-medias {
      text-align: right;
    }
  }

  html {
    font-family: 'Montserrat';
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
    height: 100%;
    width: 100%;
  }

  body {
    background: white;
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
    margin: 0;
  }

  .button--green {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #3b8070;
    color: #3b8070;
    text-decoration: none;
    padding: 10px 30px;
  }

  .button--green:hover {
    color: white;
    background-color: #3b8070;
  }

  .button--grey {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #35495e;
    color: #35495e;
    text-decoration: none;
    padding: 10px 30px;
    margin-left: 15px;
  }

  .button--grey:hover {
    color: #fff;
    background-color: #35495e;
  }

  .container {
    margin: 0 auto;
    width: 90%;
  }

  header {
    //background: $primary-color;
    background: linear-gradient(to left, #2BA54C, #5CC04A, #8FDD3D 35%);
    padding: 1em 0;
    text-align: center;

    .navbar {
      display: flex;
      justify-content: space-between;
      font-weight: bold;
    }

    a {
      color: #FFFFFF;
      text-decoration: none;

    }

    nav {
      display: flex;

      ul {
        list-style-type: none;
        padding: 0;
        display: flex;

        li a {
          font-weight: normal;
          padding: .5em;
        }
      }
    }
  }

  @media only screen and (min-width: 768px) {
    body {
      font-size: 18px;
    }
  }

</style>
