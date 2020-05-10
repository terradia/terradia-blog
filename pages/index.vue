<template>
  <div>
    <div class="hero">
      <div class="container">
        <h1>Le blog de l'application qui<br>
          facilite l'accès aux produits locaux.</h1>
      </div>
    </div>

    <div class="container">
      <main>
        <h2>Les dernières news</h2>
        <ul>
          <li v-for="post in posts">
            <img :src="post.feature_image">
            <div class="content">
              <nuxt-link :to="{ path: post.slug }">{{ post.title }}</nuxt-link>
              <p>{{ post.excerpt }}</p>
              <span>{{ post.authors[0].name }}</span>
            </div>
          </li>
        </ul>
      </main>
    </div>
  </div>
</template>

<script>
  import { getPosts } from '~/api/posts';
  export default {
    async asyncData () {
      const posts = await getPosts();
      return { posts: posts }
    }
  }
</script>

<style lang="scss" scoped>

  .hero {
    clip-path: polygon(0 0, 100% 0, 100% 68%, 0 100%);
    background: linear-gradient(to left, #2BA54C, #5CC04A, #8FDD3D 35%);
    color: white;
    text-align: center;
    padding-top: 2em;
    height: 15em;
    h1 {
      padding-top: 3em;
      margin-bottom: 1em;
      font-size: 25px;
      text-transform: uppercase;
      padding-bottom: 3em;
    }
    .hire {
      background: darken($primary-color, 10%);
      padding: .5em 3em;
      margin: 2em 0 3em;
      display: inline-block;
      border-radius: 10px;
      text-decoration: none;
    }

    p {
      margin-bottom: 2em;
      color: #35353D;
      padding-bottom: 2em;
    }
  }
  .container ul {
    list-style-type: none;
    padding: 0;
  }
  main {
    li {
      background: white;
      border-radius: 1em;
      padding: .8em;
      margin: 1em 0;
      box-shadow: 5px 21px 40px 0px rgba(0,0,0,0.3);
    }
    img {
      width: 100%;
      border-radius: .2em;
      margin-top: auto;
      margin-bottom: auto;
    }
    .content {
      padding: .5em;
    }
    a {
      font-size: 1.5em;
      text-decoration: none;
      color: #35353D;
      font-weight: bold;
      display: block;
      margin: -.1em 0 .2em;
    }
    h2 {
      padding: .8em;
      margin: 1em 0;
      color: #35353D;
      text-transform: uppercase;
      font-size: .8em;
    }
    span {
      color: $primary-color;
      text-transform: uppercase;
      font-size: 0.5em;
    }
  }
  @media only screen and (min-width: 768px) {
    main li {
      display: grid;
      grid-template-columns: 180px auto;
      grid-column-gap: 1em;
    }
  }
</style>
