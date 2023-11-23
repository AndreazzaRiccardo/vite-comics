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
            this.activeIndex = index;
        }
    }
}
</script>


<template>
    <header>
        <div class="container">
            <nav>
                <img src="../assets/img/dc-logo.png" alt="">
                <ul>
                    <li :class="{ active : activeIndex === index }" v-for="(item, index) in navItem" :key="item.name" @click="selectItemNav(index)">
                        <a href="">{{ item.name }}</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>


<style lang="scss">
@use "../style/general" as *;
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

header {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
    width: 100%;
    background-color: white
}

nav {
    @include flex(row, space-between, center);
    width: 100%;
    height: 150px;
    
    ul {
        @include flex(row, space-between, center);
        gap: 1.5rem;
        height: 100%;

        li {
            height: 100%;
            display: flex;
            align-items: center;
        }

        .active {
            border-bottom: 5px solid $bg-color;
        }

        a {
            color: black;
            font-weight: bold;
        }
    }
}
</style>
