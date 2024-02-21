<template>
  <section class="section">
    <div class="container">
      <h1 class="title">Section</h1>
      <div class="card">
        <div class="card-content">
          <div class="media">
            <div class="media-left">
              <figure class="image is-48x48">
                <img
                  src="https://bulma.io/images/placeholders/96x96.png"
                  alt="Placeholder image"
                />
              </figure>
            </div>
            <div class="media-content">
              <p class="title is-4">John Smith</p>
              <p class="subtitle is-6">@johnsmith</p>
            </div>
          </div>

          <div class="content">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus
            nec iaculis mauris. <a>@bulmaio</a>. <a href="#">#css</a>
            <a href="#">#responsive</a>
            <br />
            <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
          </div>
        </div>
      </div>
      {{ productos }}
    </div>
  </section>
</template>

<script>
const axios = require("axios").default;
export default {
  name: "Product",
  data() {
    return {
      productos: [],
    };
  },
  created() {
    this.initialize();
  },
  methods: {
    initialize() {
      return axios({
        method: "get",
        baseURL: "http://apitienda.herokuapp.com/api/v1/",
        url: "/products.json",
        responseType: "json",
      }).then((response) => {
        this.productos = response.data;
      });
    },
  },
};
</script>

<style>
</style>