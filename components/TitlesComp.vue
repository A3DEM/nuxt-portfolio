<template>
    <div class="titles">
        <div v-for="(item, index) in items" :key="index"  class="titles-container">
            <div class="titles-title">
                <h2>{{item.title}}</h2>
                <img :src="require(`@/assets/img/emoji/${item.filename}.png`)" :srcset="require(`@/assets/img/emoji/${item.filename}.webp`)" :alt="item.alt" width="20" height="20">
            </div>
            <p>{{item.paragraph}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name:"PersoComp",
        data() {
            return {
                items: [
                        {
                        title:"Propulsé par la créativité",
                        paragraph:"Chaque projet est l'opportunité de laisser parler son imagination. Découvrez la mienne au travers de mes projets !",
                        filename: "rocket",
                        alt: "Fusée"
                    },
                    {
                        title:"Guidé par le développement web",
                        paragraph:"Au cœur de ma formation, le développement web est le terrain sur lequel je peux m'exprimer. Surtout lors de projets créatifs.",
                        filename: "computer",
                        alt: "Ordinateur"
                    },
                    {
                        title:"Passionné par le football",
                        paragraph:"L'esprit d'équipe, la détermination et la rigueur sont quelques-unes de mes qualités qui découlent de mon amour du football.",
                        filename: "football",
                        alt: "Football"
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
    .titles {
        margin-top: 40px;
        &-container {
            text-align: left;
            position: relative;
            margin-bottom: 40px;
            h2 {
                margin: 0;
            }
            p {
                margin-top: 5px;
                margin-bottom: 0;
            }
            img {
                margin-left: 10px;
            }
        }
        &-title {
            display: flex;
        }   
    }
    @media screen and (min-width:1024px) {
        .titles {
            margin-left: 265px;
            margin-top: 60px;
            &-container {
                margin-bottom: 60px;
                p {
                    margin-top: 10px;
                }
                img {
                    margin-left: 15px;
                    width: 30px;
                    height: 30px;
                }
            }
        }
    }
</style>