<template>
  <div>
    <div class="hero">
      <h1>L'application qui facilite l'accès aux produits locaux.</h1>
    </div>
    <div class="content">
      <h1 v-if="error.statusCode === 404">Ooopsss.... il semblerait que tu essayes d'accèder à une page inexistante</h1>
      <h1 v-else>Nous avons rencontrés une erreur, le développeur est désolé. </h1>
      <nuxt-link to="/" class="link">Accueil</nuxt-link>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['error'],
  }
</script>

<style lang="scss" scoped>

  .content {
    flex-direction: column;
    display: flex;
    padding: 2em;
    h1{
      padding-bottom: 1em;
    }
    .link {
      text-decoration: none;
      color: black;

    }
  }



  .hero {
    h1 {
      padding-top: 3em;
      margin-bottom: 1em;
      font-size: 25px;
      text-transform: uppercase;
      padding-bottom: 3em;
    }
    clip-path: polygon(0 0, 100% 0, 100% 68%, 0 100%);
    background: linear-gradient(to left, #2BA54C, #5CC04A, #8FDD3D 35%);
    color: white;
    text-align: center;
    padding-top: 2em;
    height: 15em;
  }
</style>
