<template>
    <div class="work">
        <img :src="path">
        <div class="description">
            <p>{{ work.description }}</p>
            <p>{{ work.technologies }}</p>
        </div>
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
        max-width: 100%;
        max-height: 100%;
        object-fit: cover;
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
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        flex-direction: column;
        justify-content: center;
        top: 0;
        height: 100%;
        width: 100%;
        margin: 0;
        padding: 10px;
        text-align: center;
        z-index: 2;
        opacity: 0;
        color: white;
        background-color: rgba(12,12,12, .6);
        -moz-transition: all .3s;
        -webkit-transition: all .3s;
        transition: all .3s;
    }

    .work:hover .description,
    .work:focus .description {
        opacity: 1;
    }
</style>