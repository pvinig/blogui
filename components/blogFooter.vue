<template>
  <footer class="blog-footer">
    <div class="blog-footer__container">
      <p>
        <strong
          ><a
            href="https://instagram.com/viniciuspretto.paulo/"
            rel="noopener noreferrer"
            target="_blank"
            >Vinicius Pretto</a
          ></strong
        >
        Porto Alegre | Brasil
      </p>
      <nav>
        <a
          href="https://github.com/pvinig"
          rel="noopener noreferrer"
          target="_blank"
          title="Nosso perfil no Github"
          ><v-icon scale="2" name="brands/github" style="margin-right: 10px"
        /></a>
        <a
          href="https://instagram.com/viniciuspretto.paulo"
          rel="noopener noreferrer"
          target="_blank"
          title="Nosso perfil no Instagram"
          ><v-icon scale="2" name="brands/instagram" style="margin-right: 10px"
        /></a>
        <a
          href="https://www.linkedin.com/in/viniciuspretto/"
          rel="noopener noreferrer"
          target="_blank"
          title="Nosso perfil no Linkedin"
          ><v-icon scale="2" name="brands/linkedin" style="margin-right: 10px"
        /></a>
      </nav>
    </div>
  </footer>
</template>

<script>
export default {
  name: "BlogFooter",
};
</script>

<style lang="postcss" scoped>
.blog-footer {
  margin-top: 20px;
  padding: 15px;
  border-top: 1px solid rgba(0, 0, 0, 0.1);
  font-family: "Hind";
  background: #b9030f;

  p {
    font-weight: 300;
    letter-spacing: 0.05rem;
  }

  strong a {
    font-weight: bold;
    margin: 0;
  }

  a {
    color: #222;
    font-weight: 400;
    margin-top: 1rem;
    display: inline-block;
    margin-right: 0.5rem;
    transition: all 0.15s ease-in;

    &:hover {
      color: rgb(0, 233, 197);
    }
  }
}

.blog-footer__container {
  padding: 20px;

  @media (min-width: 992px) {
    max-width: 1200px;
    margin: 0 auto;
  }
}
</style>
