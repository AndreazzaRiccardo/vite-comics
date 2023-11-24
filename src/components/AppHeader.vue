<script>
export default {
    data() {
        return {
            navItem: ["CHARATERS","COMICS","MOVIES","TV","GAMES","COLLECTIBLES","VIDEOS","FANS","NEWS","SHOP",]
        }
    }
}
</script>


<template>
    <header>
        <div class="container">
            <nav>
                <img src="../assets/img/dc-logo.png" alt="Logo DC comics">
                <ul>
                    <li v-for="(item) in navItem" :key="item">
                        <a href="">{{ item }}</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>


<style lang="scss">
@use "../style/general";
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

            &:hover {
                border-bottom: 5px solid $bg-color;
            }
        }

        

        a {
            color: black;
            font-weight: bold;
        }
    }
}
</style>
