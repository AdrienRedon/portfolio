<template>
    <div class="work">
        <img :src="path">
        <p class="description">{{ work.description }}</p>
    </div>
</template>

<script>
    export default {
        props: ['work'],
        computed: {
            path () {
                return `/assets/img/${this.work.img}.png`;
            }
        }
    }
</script>

<style>
    .work {
        position: relative;
        height: 320px;
        width: 560px;
        overflow: hidden;
    }

    .work img {
        z-index: 1;
        height: 100%;
        width: 100%;
        -moz-transition: all .3s;
        -webkit-transition: all .3s;
        transition: all .3s;
    }

    .work:hover img,
    .work:focus img {
        -moz-transform: scale(1.1);
        -webkit-transform: scale(1.1);
        transform: scale(1.1);
    }
    .description {
        position: absolute;
        top: 0;
        height: 100%;
        width: 100%;
        line-height: 320px;
        margin: 0;
        text-align: center;
        z-index: 2;
        opacity: 0;
        color: white;
        background-color: rgba(12,12,12, .5);
        -moz-transition: all .3s;
        -webkit-transition: all .3s;
        transition: all .3s;
    }

    .work:hover .description,
    .work:focus .description {
        opacity: 1;
    }
</style>