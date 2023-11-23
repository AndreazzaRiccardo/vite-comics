<script>
export default {
  data() {
    return {
      adImgs: [
        {
          url: "digital-comics",
          title: "DIGITAL COMICS"
        },
        {
          url: "merchandise",
          title: "DC MERCHANDISE"
        },
        {
          url: "subscriptions",
          title: "SUBSCRIPTIONS"
        },
        {
          url: "shop-locator",
          title: "COMIC SHOP LOCATOR"
        },
        {
          url: "dc-power-visa",
          title: "DC POWER VISA"
        },
      ],
    }
  },
  methods: {
    getImageUrl(imgName) {
            return new URL(`../assets/img/buy-comics-${imgName}.png`, import.meta.url).href;
        }
  }
}
</script>


<template>
  <section>
    <div class="container">
      <div class="img-cont" v-for="img in adImgs">
        <img :src=getImageUrl(img.url) :alt="`Icon of ${img.title}`" >
        <h5>{{ img.title }}</h5>
      </div>
    </div>
  </section>
</template>


<style lang="scss" scoped>
@use "../style/general" as *;
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

section {
  background-color: $bg-color;

  .container {
    @include flex(row, space-between, center);
    height: 170px;
    padding: 0 2rem;
  }
}

.img-cont {
  color: white;
  @include flex(row, null, center);
  gap: 1rem;

  img {
    width: 25%;
  }
}
</style>
