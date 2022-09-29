<template>
    <div class="wrap">
        <div class="title-container">
            <span class="title">Coha Application Site Link</span>
        </div>
        <div class="spliter"></div>
        <div class="section" v-for="(value, indx) in menus" v-bind:key="indx">
            <a v-if="value.link != ''" v-bind:href="value.link" target="_blank">
                <v-btn elevation="2">{{ value.title }}</v-btn>
            </a>
            <v-btn v-else elevation="2" v-on:click="alert">{{ value.title }}</v-btn>
        </div>
    </div>
</template>

<script>
import menu from "../data/menu";
export default {
    data() {
        return {
            menus: [],
        };
    },
    mounted() {
        this.menus = menu;
    },
    methods: {
        alert() {
            alert("준비중 입니다");
        },
    },
};
</script>

<style scoped>
.spliter {
    margin: 15px;
}
.wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.section {
    padding-top: 10px;
    padding-bottom: 10px;
    width: 100%;
}
.title-container {
    width: 100%;
    text-align: center;
    height: 250px;
    background: #7f6a97;
    line-height: 250px;
}

button {
    text-transform: none;
}
a {
    text-decoration: none;
}
.title {
    font-weight: bold;
    font-size: 2em;
    color: white;
}
</style>
