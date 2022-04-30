<template>
    <div id="design">
        <h2>Projets graphisme</h2>
        <ProjectComp type="design"/>
    </div>
</template>

<script>
    import ProjectComp from "./ProjectComp.vue"
    export default {
        name:"DesignWork",
        components: {
            ProjectComp,
        },
    }
</script>

<style lang="scss" scoped>
    @media screen and (min-width:1024px) {
        #design {
            display: grid;
            grid-template-columns: 215px 1fr;
            grid-gap: 50px;
            margin-top: 60px;
        }
    }
</style>