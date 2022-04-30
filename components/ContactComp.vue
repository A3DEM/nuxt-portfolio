<template>
    <div id="contact">
        <h2>Contact</h2>
        <div class="content">
            <p>N'hésitez pas à me contacter pour plus d'informations ou pour répondre à vos questions !</p>
            <LinkComp link="mailto:ademduran6888@gmail.com" title="Envoyer un mail"/>
        </div>
    </div>
</template>

<script>
    import LinkComp from "./LinkComp.vue";
        export default {
        components: { LinkComp }
    }
</script>

<style lang="scss" scoped>
    #contact {
        p {
            margin-top: 10px;
            margin-bottom: 10px;
        }
    }
    @media screen and (min-width:1024px) {
        #contact {
            display: grid;
            grid-template-columns: 215px 1fr;
            grid-gap: 50px;
            margin-top: 60px;
            p {
                margin-top: 0px;
                margin-bottom: 20px;
            }
        }
    }
</style>