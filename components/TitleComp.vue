<template>
    <div class="title">
        <h1>Adem Duran</h1>
        <div class="subtitles">
            <h2 class="developer">Développeur junior</h2>
            <h2 class="cdb beginning">Certified Developer Boy</h2>
        </div>
        <div class="emojis">
            <div class="developer">
                <img src="@/assets/img/emoji/developer.png" alt="Développeur" width="48" height="48">
                <span>+</span>
                <img src="@/assets/img/emoji/artist.png" alt="Artiste" width="48" height="48">
                <span>+</span>
                <img src="@/assets/img/emoji/ninja.png" alt="Ninja" width="48" height="48"  @click="change()">
            </div>
            <div class="cdb beginning">
                <img src="@/assets/img/emoji/custom/js.png" alt="JavaScript" width="48" height="48">
                <span>+</span>
                <img src="@/assets/img/emoji/custom/scss.png" alt="SCSS" width="48" height="48">
                <span>+</span>
                <img src="@/assets/img/emoji/custom/vuejs.png" alt="Vue JS" width="48" height="48"  @click="change()">
            </div>
        </div>
        <div class="social-links">
            <LinkComp link="https://www.linkedin.com/in/adem-duran/" title="LinkedIn"/>
            <LinkComp link="https://github.com/A3DEM/" title="GitHub"/>
            <LinkComp link="https://dribbble.com/a3dem/" title="Dribbble"/>
            <LinkComp link="https://www.instagram.com/a3dem._/" title="Instagram"/>
        </div>
    </div>
</template>

<script>
    import LinkComp from "./LinkComp.vue";
    
    export default {
        name: "TitleComp",
        components: { LinkComp },
        data() {
            return {
                isCertified: false
            }
        },
        methods: {
            change() {

                if (!this.isCertified) {
                    
                    document.querySelectorAll(".developer").forEach(element => {
                        element.classList.add("end");
                    });
                    document.querySelectorAll(".cdb").forEach(element => {
                        element.classList.remove("beginning");
                    });
                    this.isCertified = !this.isCertified;
                } else {
                    document.querySelectorAll(".developer").forEach(element => {
                        element.classList.remove("end");
                    });
                    document.querySelectorAll(".cdb").forEach(element => {
                        element.classList.add("beginning");
                    });
                    this.isCertified = !this.isCertified;
                }

            }
        },
    }
</script>

<style lang="scss" scoped>
    @import "@/assets/scss/_vars.scss";

    .title {
        .subtitles {
            margin: 8px 0px 20px 0px;
            position: relative;
            min-height: 19px;
            h2 {
                font-size: 16px;
                font-weight: 500;
                color: $font-color;
                transition-timing-function: cubic-bezier(.65,0,.35,1);
                transition-duration: .5s;
                position: absolute;
                margin: 0;
                top: 0;
                pointer-events: all;
                left: 0;
            }
        }
        .emojis {
            position: relative;
            min-height: 48px;
            div {
                position: absolute;
                top: 0;
                left: 0;
                display: flex;
                align-items: center;
                transition-timing-function: cubic-bezier(.65,0,.35,1);
                transition-duration: .5s;
                transition-delay: 0.1s;
                pointer-events: all;
                span {
                    margin: 0px 12px;
                }
            }
        }
        .subtitles .end, .emojis .end {
            transform: translateX(100px);
            opacity: 0;
            pointer-events: none;
        }
        .subtitles .beginning, .emojis .beginning {
            transform: translateX(-100px);
            opacity: 0;
            pointer-events: none;
        }
        .social-links {
            margin-top: 20px;
            display: flex;
            flex-wrap: wrap;
        }
    }
    @media screen and (min-width:1024px) {
        .title {    
            h1 {
                line-height: 28px;
                margin-top: 55px;
            }
            .subtitles {
                min-height: 29px;
                margin-bottom: 30px;  
                h2 {
                    font-size: 24px;
                }
            }
            .emojis {
                font-size: 18px;
                img {
                    width: 60px;
                    height: auto;
                }
            }
            .social-links {
                margin-top: 30px;
            }
        }
    }
</style>