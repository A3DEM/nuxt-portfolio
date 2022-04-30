<template>
    <div id="web">
        <h2>Projets web</h2>
        <ProjectComp type="web"/>
    </div>
</template>

<script>
    import ProjectComp from "./ProjectComp.vue"
    export default {
        name:"WebWork",
        components: {
            ProjectComp,
        }
    }
</script>

<style lang="scss" scoped>
    @media screen and (min-width:1024px) {
        #web {
            display: grid;
            grid-template-columns: 215px 1fr;
            grid-gap: 50px;
            margin-top: 60px;
        }
    }
</style>