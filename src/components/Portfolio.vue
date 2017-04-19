<template>
    <portfolio-section>
        <h2>Portfolio</h2>
        <div class="works">
            <div class="work">
                <img src="/assets/img/cpe-calendar.png">
            </div>
            <div class="work">
                <img src="/assets/img/ludofactory.png">
            </div>
            <div class="work">
                <img src="/assets/img/relaxapic.png">
            </div>
            <div class="work">
                <img src="/assets/img/steadytrip.png">
            </div>
            <div class="work">
                <img src="/assets/img/thelatest.png">
            </div>
        </div>
    </portfolio-section>
</template>

<script>
    import PortfolioSection from './PortfolioSection.vue';

    export default {
        components: {
            PortfolioSection,
        }
    }
</script>

<style scoped>
    .works {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
    }
    .work img {
        height: 320px;
        width: 560px;
    }
</style>