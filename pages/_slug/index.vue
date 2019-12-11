<template>
  <div class="container">
    <h1>{{ post.title }}</h1>
    <main class="main">
      <div class="content">
        <img :src="post.feature_image">
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

<style lang="scss" scoped>

  .container {
    overflow: hidden;
  }

  .article {
    display: flex;
    align-content: center;
    text-align: center;
    justify-content: center;
    flex-direction: column;
    align-items: center;
  }

  h1 {
    margin-top: 1em;
    background-color: white;
    border-radius: 0.5em;
    text-align: center;
    //padding: 1em;
    //box-shadow: 5px 21px 40px 0px rgba(0,0,0,0.3);
  }

  .main {
    padding-bottom: 1em;
  }

  .content {
    display: block;
    align-items: center;
    justify-content: center;
    align-content: center;
    margin-top: 1em;
    background-color: white;
    border-radius: 1em;
    padding: 1em;
    //box-shadow: 5px 21px 40px 0px rgba(0,0,0,0.3);
  }

  img {
    margin-bottom: 3em;
    width: 100%;
  }

  @media only screen and (min-width: 768px) {
    .content {
      padding: 2em;
    }
  }
</style>
