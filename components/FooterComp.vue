<template>
    <footer>
       Made with <img src="@/assets/img/emoji/heart.png" srcset="@/assets/img/emoji/heart.webp" alt="Love" height="15" width="15" loading="lazy"> + <img src="@/assets/img/svg/vuejs.svg" alt="Vue JS" height="15" width="15" loading="lazy"> in Mulhouse, France.
    </footer>
</template>

<script>
    export default {
        name: "FooterComp"
    }
</script>

<style lang="scss" scoped>
    footer {
        font-size: 14px;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        margin-top: 30px;
        font-weight: bold;
        img {
            margin: 0px 5px;
        }
    }
    @media screen and (min-width:1024px) {
        footer {
            font-size: 24px;
            margin-left: 265px;
            margin-top: 60px;
            img {
                width: 25px;
                height: auto;
                margin: 0px 8px;
            }
        }
    }
</style>