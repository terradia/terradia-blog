<template>
  <div class="container">
    <h1 style="color: #2BA54C">{{ post.title }}</h1>
    <main class="main">
      <div class="content">
<!--        <img :src="post.feature_image">-->
        <div v-html="post.html" class="article"></div>
      </div>
    </main>
  </div>
</template>

<script>
  import {getSinglePost} from '~/api/posts';

  export default {
    async asyncData({params}) {
      const post = await getSinglePost(params.slug);
      console.log(post);
      return {
        post: post
      }
    }
  }
</script>

<style lang="scss">
  .kg-image {
    width: 60%;
  }

  .kg-image-card {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
  }

  h3 {
    color: #2BA54C;
  }

  strong {
    color: #5CC04A;
  }

</style>

<style lang="scss" scoped>

  .container {
    overflow: hidden;
  }

  .content {
    display: block;
    margin-top: 1em;
    background-color: white;
    border-radius: 1em;
    padding: 1em;
    align-items: center;
  }

  .article {
    display: flex;
    align-content: center;
    text-align: justify;
    flex-direction: column;
    margin: 3em;
    color: #35353D;
  }

  h1 {
    margin-top: 1em;
    background-color: white;
    border-radius: 0.5em;
    text-align: center;
  }

  .main {
    padding-bottom: 1em;
  }



  img {
    margin-bottom: 3em;
    width: 10em;
  }

  @media (max-width: 500px) {
    .article {
      margin: 0em;
    }

  }
</style>
