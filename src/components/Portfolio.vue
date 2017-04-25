<template>
    <portfolio-section>
        <h2>Portfolio</h2>
        <div class="works">
            <work v-for="work in works" :work="work"></work>
        </div>
    </portfolio-section>
</template>

<script>
    import PortfolioSection from './PortfolioSection.vue';
    import Work from './Work.vue';

    export default {
        components: {
            PortfolioSection,
            Work,
        },
        data () {
            return {
                works: [
                    {img: 'cpe-calendar', description: 'Java, MySQL'},
                    {img: 'ludofactory', description: 'Ruby, Ruby on Rails'},
                    {img: 'relaxapic', description: 'PHP, MySQL, Javascript'},
                    {img: 'steadytrip', description: 'C#, NodeJS, VueJS, SQL Server'},
                    {img: 'thelatest', description: 'PHP, Symfony 2, Angular'},
                ]
            }
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
    
</style>