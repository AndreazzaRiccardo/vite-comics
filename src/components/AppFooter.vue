<script>
export default {
  data() {
    return {
      footerList: [
        {
          title: "DC COMICS",
          list: ["Charaters", "Comics", "Movies", "TV", "Games", "Videos", "News"]
        },
        {
          title: "DC",
          list: ["Terms Of Use", "Privacy Policy (New)", "Ad Choices", "Advertising", "Jobs", "Subscriptions", "Talent Workshop", "CPSC Certificates", "Rating", "Shop Help", "Contact Us"]
        },
        {
          title: "SITES",
          list: ["DC", "MAD Magazine", "DC Kids", "DC Universe", "DC Power Visa"]
        },
        {
          title: "SHOP",
          list: ["Shop DC", "Shop DC Collectibles"]
        }
      ],
      socialList: [
        {
          icon: "facebook",
          link: "www.facebook.com"
        },
        {
          icon: "twitter",
          link: "www.twitter.com"
        },
        {
          icon: "youtube",
          link: "www.youtube.com"
        },
        {
          icon: "pinterest",
          link: "www.pinterest.com"
        },
        {
          icon: "periscope",
          link: "www.periscope.com"
        }
      ]
    }
  },
  methods: {
    getImageUrl(imgName) {
      return new URL(`../assets/img/footer-${imgName}.png`, import.meta.url).href;
    }
  }
}
</script>


<template>
  <footer>
    <section class="top-footer-section container">
      <div class="footer-list">
        <div v-for="objList in footerList" class="link-list">
          <h4>{{ objList.title }}</h4>
          <ul>
            <li v-for="item in objList.list"><a href="">{{ item }}</a></li>
          </ul>
        </div>
      </div>
      <div class="dc-bg"></div>
    </section>

    <section class="bottom-footer-section">
      <div class="container">
        <button>SIGN-UP NOW!</button>
        <div class="social-list">
          <h3>FOLLOW US</h3>
          <ul>
            <li v-for="social in socialList">
              <a :href="`http://${social.link}`"><img :src=getImageUrl(social.icon) :alt="`Icon of ${social.icon}`"></a>
            </li>
          </ul>
        </div>
      </div>
    </section>
  </footer>
</template>


<style lang="scss" scoped>
@use "../style/general";
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

footer {
  width: 100%;
  background-image: url(../assets/img/footer-bg.jpg);
}

.top-footer-section {
  min-height: 400px;
  color: white;
  @include flex(row, space-between, null);

  .dc-bg {
    background-position: center;
    background-repeat: no-repeat;
    background-image: url(../assets/img/dc-logo-bg.png);
    width: 50%;
  }

  .footer-list {
    display: flex;
    padding: 2rem 0;
    flex-wrap: wrap;
    width: calc(1200px / 3);
    justify-content: space-between;

    a {
      color: gray;
      font-size: .8rem;
    }

    .link-list{
      h4 {
        margin-bottom: 1rem;
      }
      ul {
        display: flex;
        flex-direction: column;
        gap: .3rem;
      }
    }
  }
}

.bottom-footer-section {
  height: 100px;
  background-color: $bg-dark-color;

  .container {
    @include flex(row, space-between, center);
    height: 100%;

    button {
      border: 2px solid $bg-color;
      padding: .8rem 1rem;
      background-color: $bg-dark-color;
      color: white;
      font-weight: bolder;

      &:hover {
        background-color: lighten($bg-dark-color, 20%);
        cursor: pointer;
        border: 3px groove;
      }
    }
  }

  .social-list {
    color: $bg-color;
    @include flex(row, space-between, center);
    ul {
      @include flex(row, space-between, center);
      gap: 1rem;
      margin-left: 1rem;
    }
  }
}
</style>
