<template>
    <a :href="link" target="_blank">{{title}}</a>
</template>

<script>
    export default {
        name: "LinkComp",
        props: {
            link: {
                type: String,
                default: "https://figma.com/" 
            },
            title: {
                type: String,
                default:"Lien"
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "@/assets/scss/_vars.scss";

    a {
        color: $link-color;
        text-decoration: none;
        margin-right: 12px;
    }
    .no-margin {
        margin: 0;
    }
    @media screen and (min-width:1024px) {
        a {
            margin-right: 18px;
        }
    }
</style>