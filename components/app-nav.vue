<template>
<nav id="top">
  <div class="wrapper">
      <h1 data-aos="fade"><nuxt-link to="/">ENLIGHTENMENT</nuxt-link></h1>

      <ul class="categories">
        <li v-for="(item, index) in categories" v-bind:key="index" data-aos="fade-up">
          <nuxt-link v-bind:to="'/' + (item.to || urlize(item))">
            {{ item.label || item }}
          </nuxt-link>
        </li>
      </ul>
  </div>
</nav>
</template>

<script>
import { urlize } from "~/assets/functions.js";

export default {
  data() {
    return {
      categories: [
        "World",
        "Science",
        "Technology",
        "Business",
        "Books",
        "Music",
        "Film",
        "Games",
        "Stage",
        "Fashion"
      ]
    };
  },
  methods: {
    urlize
  }
};
</script>

<style lang="postcss" scoped>
@import "../assets/variables.css";

nav {
  color: var(--white);
  background-color: var(--black);
  box-shadow: var(--shadow);
}

a {
  color: var(--white);
}

h1 {
  text-align: center;
  margin: 0.5rem 0;
}

ul {
  list-style-type: none;
  padding-left: 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  text-align: right;

  @media (--lg) {
    justify-content: space-between;
  }

  & li {
    & a {
      display: block;
      padding: 0.5rem 1rem;

      @media (--lg) {
        padding-left: 0.5rem;
        padding-right: 0.5rem;
      }
    }
  }
}
</style>
