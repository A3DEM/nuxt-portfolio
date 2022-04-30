<template>
    <header>
        <img class="me" src="@/assets/img/photo-presentation-small.jpg" srcset="@/assets/img/photo-presentation-small.webp" alt="C'est moi !" width="110" height="110">
        <div :class="{switch:true, active: isActive }">
            <div class="switch-img">
                <img src="@/assets/img/emoji/sun.png" alt="Light Mode" width="30" height="30">
            </div>
            <div class="switch-item" @click="isActive = !isActive; $emit('toggle')">
                <input type="button" class="switch-toggle">
            </div>
            <div class="switch-img">
                <img src="@/assets/img/emoji/moon.png" alt="Dark Mode" width="26" height="26">
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        name:"HeaderComp",
        props: ["mode"],
        data() {
            return {
                isActive: true
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "@/assets/scss/_vars.scss";

    header {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        img {
            border-radius: 1000px;
        }
        .switch {
            display: flex;
            align-items: center;
            align-self: flex-start;
            margin-top: 10px;   
            &-item {
                background-color: $switch-color;
                width: 50px;
                border-radius: 100px;
                margin: 0px 10px;
                padding: 3px 5px;
                display: flex;
                align-content: center;
            }
            &-toggle {
                background-color: $switch-button-color;
                width: 25px;
                height: 25px;
                border-radius: 100px;
                border: none;
            }
            &-img {
                display: flex;
                align-content: center;
            }
        }
        .active {
            .switch-item {
                background-color: $switch-active-color;
            }
            .switch-toggle {
                transform: translateX(100%);
            }
        }
    }
    @media screen and (min-width:375px) {
        header {
            flex-direction: row;
            .switch {
                margin-left: auto;
            }
        }
    }
    @media screen and (min-width:1024px) {
        header {
            display: inline-flex;
            flex-direction: column;
            .me {
                width: 215px;
                height: auto;
            }
            .switch {
                margin-right: auto;
                margin-top: 15px;
            }
        }
    }
</style>