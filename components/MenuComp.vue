<template>
    <nav id="menu">
        <div :class="{container:true, opened: isOpen }">
            <div :class="{burger:true, open: isOpen }" @click="isOpen = !isOpen;">
                <div class="burger-element"></div>
                <div class="burger-element"></div>
                <div class="burger-element"></div>
            </div>
            <ul>
                <li>
                    <a href="#about-me" :class="{clicked: isClicked == 1}" @click="clickedElement(1)">
                        <div class="emoji">
                            <img src="@/assets/img/emoji/me.png" srcset="@/assets/img/emoji/me.webp" alt="À propos" width="35" height="35" loading="lazy">
                        </div>
                        <p>À propos</p>
                    </a>
                </li>
                <li>
                    <a href="#web" :class="{clicked: isClicked == 2}" @click="clickedElement(2)">
                        <div class="emoji">
                            <img src="@/assets/img/emoji/computer.png" srcset="@/assets/img/emoji/computer.webp" alt="Web" width="35" height="35" loading="lazy">
                        </div>
                        <p>Web</p>
                    </a>
                </li>
                <li>
                    <a href="#design" :class="{clicked: isClicked == 3}" @click="clickedElement(3)">
                        <div class="emoji">
                            <img src="@/assets/img/emoji/design.png" srcset="@/assets/img/emoji/design.webp" alt="Design" width="35" height="35" loading="lazy">
                        </div>
                        <p>Graphisme</p>
                    </a>
                </li>
                <li>
                    <a href="#contact" :class="{clicked: isClicked == 4}" @click="clickedElement(4)">
                        <div class="emoji">
                            <img src="@/assets/img/emoji/contact.png" srcset="@/assets/img/emoji/contact.webp" alt="Contact" width="35" height="35" loading="lazy">
                        </div>
                        <p>Contact</p>
                    </a>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
    export default {
        name: "MenuComp",
        data() {
            return {
                isOpen: false,
                isClicked : false
            }
        },
        methods: {
            clickedElement(number) {
                this.isClicked = number;
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "@/assets/scss/_vars.scss";

    #menu {
        position: fixed;
        z-index: 99;
        bottom: 0;
        left: 0;
        right:0;
        padding: 50px;
        pointer-events: none;
        .container {
            display: flex;
            flex-direction: column;
            align-items: flex-end;      
            transform: translateY(88%);
            pointer-events: auto;
            .burger {   
                background-color: $light-menu-color;
                backdrop-filter: blur(4px);
                display: flex;
                flex-direction: column;
                padding: 13px 10px;
                border-radius: 15px;
                &-element {
                    width: 26px;
                    height: 3px;
                    background-color: white;
                }
                &-element:nth-child(1), &-element:nth-child(3)  {
                    transform-origin: center center;
                }
                &-element:nth-child(2) {
                    margin: 5px 0px;
                }
            }
            .open {
                .burger-element:first-child {
                    transform: translateY(275%) rotate(45deg);
                }
                .burger-element:nth-child(2) {
                    opacity: 0;
                }
                .burger-element:last-child {
                    transform: translateY(-275%) rotate(-45deg);
                }
            }
            ul {
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                align-items: center;
                background-color: $light-menu-color;
                backdrop-filter: blur(4px);
                border-radius: 20px;
                list-style-type: none;
                padding: 20px 12px;
                margin-top: 50px;
                text-align: center;
                li {
                    flex: 30%;
                    margin: 0px 8px;
                    a {  
                        color: $light-title-color;
                        text-decoration: none;
                        .emoji {
                            background-color: white;
                            border-radius: 10px;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                            width: 60px;
                            height: 60px;
                            margin: auto;
                        }
                        p {
                            margin: 4px 0px;
                            margin-top: 4px;
                        }
                    }
                    .clicked {
                        .emoji {
                            background-color: $link-color;
                        }
                        p {
                            color: $link-color;
                        }
                    }
                }
            }
        }
        .opened {
            transform: translateY(1%);
            ul {
                margin-top: 20px;
            }
        }
    }
    @media screen and (min-width:425px) {
        #menu {
            .container {
                ul {
                    flex-wrap: nowrap;
                }
            }
        }
    }
    @media screen and (min-width: 1024px) {
        #menu {
            bottom: unset;
            left: unset;
            top: 0; 
            .container { 
                flex-direction: column-reverse;
                transform: translateY(-72%);
                .burger {   
                    padding: 18px 16px;
                    &-element {
                        width: 30px;
                        height: 4px;
                    }
                }
                .open {
                    .burger-element:first-child {
                        transform: translateY(225%) rotate(45deg);
                    }
                    .burger-element:nth-child(2) {
                        opacity: 0;
                    }
                    .burger-element:last-child {
                        transform: translateY(-225%) rotate(-45deg);
                    }
                }
                ul {
                    margin-top: 0;
                    margin-bottom: 70px;
                    li { 
                        a {
                            .emoji {
                                height: 70px;
                                width: 70px;
                                img {
                                    width: 50px;
                                    height:50px;
                                }
                            }
                            p {
                                font-size: 14px;
                                margin-bottom: 0;
                            }
                        }
                    }
                }
            }
            .opened {
                transform: translateY(1%);
            }
        }
    }
    @media screen and (min-width:1440px) {
        #menu {
            .container {
                transform: translateY(0%);
                .burger {
                    display: none;
                }
                ul {
                    margin: 0;
                    flex-direction: column;
                    li {
                        a {
                            .emoji {
                                height: 70px;
                                width: 70px;
                                img {
                                    width: 50px;
                                    height: 50px;
                                }
                            }
                            p {
                                font-size: 16px;
                                margin-bottom: 16px;
                            }
                        }
                    }
                    li:last-child {
                        p {
                            margin-bottom: 0;
                        }
                    }
                }
            }
        }
    }
</style>