<script>
export default {
    data() {
        return {
            activeIndex: "",
            navItem: [
            {
                name: "CHARATERS",
                active: false
            },
            {
                name: "COMICS",
                active: false
            },
            {
                name: "MOVIES",
                active: false
            },
            {
                name: "TV",
                active: false
            },
            {
                name: "GAMES",
                active: false
            },
            {
                name: "COLLECTIBLES",
                active: false
            },
            {
                name: "VIDEOS",
                active: false
            },
            {
                name: "FANS",
                active: false
            },
            {
                name: "NEWS",
                active: false
            },
            {
                name: "SHOP",
                active: false
            }
            ],
        }
    },
    methods: {
        selectItemNav(index) {
            this.activeIndex = index
        }
    }
}
</script>

<template>
  <div class="container">
    <header>
        <nav>
            <img src="../assets/img/dc-logo.png" alt="">
            <ul>
                <li :class="{ active : activeIndex === index }" v-for="(item, index) in navItem" :key="item.name" @click="selectItemNav(index)">
                    <a href="">{{ item.name }}</a>
                </li>
            </ul>
        </nav>
    </header>
  </div>
</template>

<style lang="scss">
@use "../style/general.scss" as *;
@use "../style/partials/mixins.scss" as *;

nav {
    @include flex(row, space-between, center);
    padding: 1.5rem 0;
    height: 150px;
    
    ul {
        list-style: none;
        @include flex(row, space-between, center);
        gap: 1rem;
        height: 100%;

        li {
            height: 100%;
            display: flex;
            align-items: center;
        }

        .active {
            border-bottom: 5px solid var(--bg-blue);
        }

        a {
            color: black;
            font-weight: bold;
        }
    }
}



</style>
