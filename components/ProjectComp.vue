<template>
    <div class="projects">
        <div class="type" v-if="type == 'web'">
            <div v-for="(project, index) in webProjects" :key="index" class="project">
                <h3>{{ project.title }}</h3>
                <p>{{ project.paragraph }}</p>
                <div class="links">
                    <LinkComp :link="project.links[0].demo" title="Voir le projet" />
                    <LinkComp :link="project.links[0].sourceCode" title="Voir le code source" />
                </div>
            </div>
        </div>
        <div class="type" v-else-if="type == 'design'">
            <div v-for="(project, index) in designProjects" :key="index" class="project">
                <h3>{{ project.title }}</h3>
                <p>{{ project.paragraph }}</p>
                <div class="links">
                    <LinkComp :link="project.link" title="Voir le projet" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import LinkComp from "./LinkComp.vue"
export default {
    name: "ProjectComp",
    components: {
        LinkComp
    },
    props: {
        type: {
            type: String,
            default: "web"
        }
    },
    data() {
        return {
            webProjects: [
                {
                    title: "[WIP] Application de recettes",
                    paragraph: "Dans le cadre de notre module de Vue, nous devons développer une application de recettes. Elle s'appuie sur une API faite par l'enseignant. Le projet nous permet de mettre en pratique plusieurs aspects fondamentaux de Vue comme les components, les props, les emits et entre autres l'utilisation d'Axios ! (Le projet est toujours en cours de réalisation. Si les recettes ne s'affichent pas, attendez que l'API se lance)",
                    links: [{
                        demo: "https://master--clever-kringle-b55b7d.netlify.app/",
                        sourceCode: "https://github.com/A3DEM/vue-js-recipe-app/tree/master/recipe-app"
                    }]
                },
                {
                    title: "BMW M4",
                    paragraph: "Ce projet a pour but de présenter la BMW M4. Une attention particulière a été donnée au chargement. L'animation a été faite grâce à la librairie GSAP.",
                    links: [{
                        demo: "https://a3dem.github.io/site_bmw/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/site_bmw/"
                    }]
                },
                {
                    title: "Mocha café",
                    paragraph: "Lors de ma recherche de stage de 2ème année, j’ai effectué des tests au sein de l’entreprise Numendo. Je devais reproduire une maquette autour de la thématique du café. Voici le résultat du projet.",
                    links: [{
                        demo: "https://a3dem.github.io/mocha_cafe_numendo/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/mocha_cafe_numendo/"
                    }]
                },
                {
                    title: "Les cartes projets",
                    paragraph: "Lors du développement de mon portfolio, j’ai décidé de créer des cartes projets personnalisés. Voici le résultat ! Un effet de mouvement a été ajouté à la première carte en utilisant la libraire tilt.js.",
                    links: [{
                        demo: "https://a3dem.github.io/card_projets/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/card_projets/"
                    }]
                },
                {
                    title: "Matrix",
                    paragraph: "À l’occasion de la sortie du dernier film Matrix, j’ai tenté de créer une page qui reprend la direction artistique du 4ème volet de la saga.",
                    links: [{
                        demo: "https://a3dem.github.io/matrix/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/matrix/"
                    }]
                },
                {
                    title: "Calculatrice de matrices",
                    paragraph: "Afin de vérifier mes calculs pour mon module de maths pour le web, j’ai codé une calculatrice de matrices qui permet d’effectuer un produit matriciel.",
                    links: [{
                        demo: "https://a3dem.github.io/inte_web/calculatrice_matrice/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/inte_web/calculatrice_matrice/"
                    }]
                },
                {
                    title: "Fonctions mathématiques",
                    paragraph: "Dans le cadre du module de mathématiques, nous avons dû créer un ensemble de fonctions mathématiques. Ce projet de première année permet de calculer le PGCD, le PPCM, les coefficients de Bézout ainsi que la factorisation en nombres premiers pour deux nombres donnés, mais également de chiffrer votre message selon le décalage que vous souhaitez.",
                    links: [{
                        demo: "https://a3dem.github.io/inte_web/projet_maths/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/inte_web/projet_maths"
                    }]
                },
                {
                    title: "Mercedes-Benz",
                    paragraph: "Cette page web reprend une maquette trouvée sur Dribbble. Pour ce projet, j'ai pu expérimenter des animations spéciales, notamment grâce au titre qui se dévoile au fur et à mesure.",
                    links: [{
                        demo: "https://a3dem.github.io/inte_web/site_mercedes/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/inte_web/site_mercedes/"
                    }]
                },
                {
                    title: "Ancien portfolio Angular",
                    paragraph: "Accompagné d’un ingénieur études et développement de SFEIR Strasbourg, j’ai pu créer mon portfolio sous Angular en reprenant un thème HTML pré-construit. Le principal objectif de ce projet était de mieux connaître l’environnement Angular.",
                    links: [{
                        demo: "https://portfolio-ademduran.web.app/",
                        sourceCode: "https://github.com/A3DEM/portfolio-ademduran/"
                    }]
                },
                {
                    title: "Switch Jour-Nuit",
                    paragraph: "Jouez avec le switch pour découvrir ce qu’il déclenche !",
                    links: [{
                        demo: "https://a3dem.github.io/inte_web/switch_jour_nuit/",
                        sourceCode: "https://github.com/A3DEM/a3dem.github.io/tree/master/inte_web/switch_jour_nuit/"
                    }]
                },
            ],
            designProjects: [
                {
                    title: "Euro 2021",
                    paragraph: "À l’occasion de l’Euro 2021, j’ai produit une affiche pour le match France-Suisse. Vous pouvez également trouver un autre poster sur mon compte Dribbble.",
                    link: "https://dribbble.com/shots/17827581--Euro-2021-France-Suisse/"
                },
                {
                    title: "Whistle",
                    paragraph: "Étant un grand fan de football, j’ai imaginé le logo d’un réseau social pour fans. À long terme, mon projet serait de designer l’interface de cette application et de la développer !",
                    link: "https://dribbble.com/shots/18031119-Whistle-Football-App/"
                },
                {
                    title: "Trinity Featuring Interface",
                    paragraph: "C’est avec un style atypique que le rappeur Laylow s’est imposé dans l’industrie musicale. Avec son univers digital, il a marqué l’année 2020 grâce à son projet TRINITY. Innovateur, l’album se veut être un « logiciel de stimulation émotionnelle ». Afin de présenter son album, j'ai créé une vidéo qui s'inscrit dans la direction artistique du projet : la Trinity Featuring Interface.",
                    link: "https://youtu.be/fJf7ypvdq2E/"
                },
                {
                    title: "L'Étrange Histoire de Mr. Anderson",
                    paragraph: "Avec son nouveau projet, Laylow a su confirmer qu'il était définivement le Man of the Year. L'Étrange Histoire de Mr. Anderson, sorti après TRINITY, apporte son lot de nouveautés. La Trinity Featuring Interface se met à jour et devient la Digitalmundo Featuring Interface.",
                    link: "https://youtu.be/iHKKcfcYXls/"
                },
                {
                    title: "Carte Vladimir Cauchemar",
                    paragraph: "Vladimir Cauchemar a sorti son projet BRRR. J'ai décidé de créer une carte en 3D de l'artiste. L'objectif de la carte est de reprendre le concept qui avait été mis en place pour l'annonce du projet.",
                    link: "https://dribbble.com/shots/18036866--WIP-Carte-Vladimir-Cauchemar/"
                },
                {
                    title: "Carte Gold | Carte Noire",
                    paragraph: "Originaire de la Courneuve, le rappeur Dinos a partagé deux titres avant la sortie de son premier album. Ces deux morceaux, respectivement Carte Gold et Carte Noire, servaient à faire la promotion de ce dernier. J’ai donc imaginé deux vraies cartes bancaires à l’effigie du rappeur.",
                    link: "https://dribbble.com/shots/18037874-Carte-Gold-Carte-Noire/"
                },
                {
                    title: "Ultra",
                    paragraph: "Au cours de l’année 2021, le rappeur Booba a sorti son dernier album intitulé « Ultra ». Afin de célébrer la sortie de l’album, j’ai créé une pochette fictive du projet en 3D.",
                    link: "https://dribbble.com/shots/18036843-Ultra/"
                },
                {
                    title: "Burak « Kral » Yilmaz",
                    paragraph: "2021 sera également marquée par le sacre du LOSC en tant que champion de France. À cette occasion, j’ai réalisé un montage mettant en scène Burak Yilmaz, joueur clé de ce titre, en roi (kral en turc).",
                    link: "https://dribbble.com/shots/18036797-Burak-Kral-Y-lmaz/"
                },
                {
                    title: "Otto",
                    paragraph: "Otto. C’est à travers ces quatre lettres que le rappeur SCH nous parle de son père dans le titre éponyme, issu de son album JVLIVS. L’illustration a pour but d’être une pochette pour le morceau.",
                    link: "https://dribbble.com/shots/18036825-Otto/"
                },
                {
                    title: "Project Resident Evil 2",
                    paragraph: "Propulsé sur Orion, une console fictive, redécouvrez Resident Evil 2, un jeu d'horreur sorti en 1998 et réadapté en 2019. Après avoir eu une très bonne expérience avec la version sortie en 2019, j'ai décidé de créer des modèles 3D des armes de Leon S. Kennedy (l'un des personnages principaux) et d’autres éléments du jeu.",
                    link: "https://youtu.be/5Pu63s0hg-c/"
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/_vars.scss";

.projects {
    .project {
        p {
            margin-top: 10px;
            margin-bottom: 0;
        }

        .links {
            margin-top: 10px;
        }
    }
}

@media screen and (min-width:1024px) {
    .projects {
        .project {
            p {
                margin-top: 20px;
            }

            .links {
                margin-top: 20px;
            }
        }

        .project:first-child {
            h3 {
                margin-top: 0;
            }
        }
    }
}
</style>