<template>
    <portfolio-section class="inverted">
        <response v-if="showingPopup">{{ response }}</response>
        <h2>Contact</h2>
        <form @submit="sendMail">
            <label for="mail">Votre adresse mail</label>
            <input type="mail" id="mail" name="mail" v-model="email">
            <label for="content">Votre message</label>
            <textarea name="content" id="content" v-model="content"></textarea>
            <div class="g-recaptcha" :data-sitekey="siteKey"></div>
            <button class="btn" type="submit">Envoyer</button>
        </form>
        <p>Vous pouvez me retrouver sur les réseaux sociaux</p>
        <ul>
            <li><a href="https://twitter.com/adrienredon"><i class="fa fa-twitter" aria-hidden="true"></i></a></li>
            <li><a href="https://github.com/adrienredon"><i class="fa fa-github" aria-hidden="true"></i></a></li>
            <li><a href="https://www.linkedin.com/in/adrienr/"><i class="fa fa-linkedin" aria-hidden="true"></i></a></li>
        </ul>
    </portfolio-section>
</template>

<script>
    import axios from 'axios';
    import PortfolioSection from './PortfolioSection.vue';
    import Response from './Response.vue';

    export default {
        data () {
            return {
                siteKey: '6LcWOhsUAAAAAPLMXiySz3iSFrLanPU53Uc7pCxi',
                showingPopup: false,
                response: '',
                email: '',
                content: '',
            }
        },
        components: {
            PortfolioSection,
            Response,
        },
        methods: {
            sendMail (event) {
                event.preventDefault();
                const data = new FormData(event.target);
                axios
                    .post('/sendmail.php', data)
                    .then(resp => this.showResponse(resp.data));
                ;
            },
            showResponse (resp) {
                this.response = resp;
                this.showingPopup = true;
                this.email = '';
                this.content = '';
                setTimeout(() => this.showingPopup = false, 5000);
            }
        }
    }
</script>

<style scoped>

    .inverted {
        background-color: #F05F40;
        color: #FFF;
    }
    form {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        flex-direction: column;
    }
    label, input, textarea {
        margin: 0 auto;
        width: 80%;
        max-width: 600px;
        font-size: 1rem;
    }
    input, textarea {
        margin-bottom: 20px;
    }
    textarea {
        min-height: 6rem;
    }
    button {
        width: 120px;
        margin: auto;
    }
    .g-recaptcha {
        margin: auto;
    }

    p {
        text-align: center;
    }
    ul {
        max-width: 800px;
        margin: auto;
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        list-style-type: none;
        justify-content: space-around;
    } 
    a {
        padding: 20px;
    }
    .fa {
        font-size: 42px;
        color: white;
    }
    a:hover .fa-twitter {
        color: #0084b4;
    }
    a:hover .fa-github {
        color: #333;
    }
    a:hover .fa-linkedin {
        color: #0077b5;
    }

    .btn {
        display: inline-block;
        margin: 20px auto;
        height: 36px;
        line-height: 36px;
        vertical-align: middle;
        padding: 0 2rem;

        text-align: center;
        text-decoration: none;
        letter-spacing: .5px;
        
        background-color: white;
        border: none;
        border-radius: 2px;
        
        text-transform: uppercase;
        transition: .2s ease-out;
        cursor: pointer;
    }
</style>