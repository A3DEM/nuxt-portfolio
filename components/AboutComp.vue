<template>
    <div id="about-me">
        <h2>À propos</h2>
        <div class="content">
            <p>Fan de football, curieux et polyvalent, je suis étudiant en Licence professionnelle en Webdesign-Webdéveloppement ainsi qu’en alternance au sein de l’agence <LinkComp class="no-margin" title="Première Place" link="https://www.premiere.place/"/> à Mulhouse ! </p>
            <p>Actuellement, je suis à la recherche d’une entreprise pour y effectuer mon mastère en Développement Web/Tech Lead chez Digital Campus Bordeaux.</p>
            <p>Découvrez ma personnalité, mon parcours et mes expériences à travers mon CV !</p>
            <LinkComp link="/DURAN-Adem-CV.pdf" download title="Télécharger le CV"/>
        </div>
    </div>
</template>

<script>
    import LinkComp from "./LinkComp.vue";
        export default {
        name: "TitleComp",
        components: { LinkComp }
    }
</script>

<style lang="scss" scoped>
    @media screen and (min-width:1024px) {
        #about-me {
            display: grid;
            grid-template-columns: 215px 1fr;
            grid-gap: 50px;
            .content {
                p {
                    &:first-child {
                        margin-top: 0;
                    }
                }
            }
        }
    }
</style>