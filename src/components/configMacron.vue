<script>
    import emailjs from '@emailjs/browser';
    import { ref } from 'vue'

    export default {
        setup(){
            const userEmail = ref('');

            return {
                userEmail,
            };
        },
        methods: {
            handleClick() {
                this.$emit('buttonClick');
            },

            updateVelkost(value) {
                this.vyber.velkost = value;
                if (this.vyber.velkost === "teaser"){
                    this.vyber.prichut = '';
                }
                console.log(this.vyber);
            },

            updatePrichut(value){
                if (this.vyber.velkost !== "teaser"){
                    this.vyber.prichut = value;
                }
            },

            checkAnswerAndSendEmail() {
                const correctAnswer = this.num1 + this.num2;
                if (parseInt(this.userAnswer, 10) === correctAnswer) {
                    this.resultMessage = 'Správne! Nie si robot.';
                    this.sendEmail();
                } else {
                    this.resultMessage = 'Nesprávne. Skús to znova.';
                }
            },

            sendEmail(){
                const emailData = {
                    velkost: this.vyber.velkost,
                    prichut: this.vyber.prichut,
                    userEmail: this.vyber.userEmail,
                };

                emailjs.send('service_h0dylce', 'template_lio20py', emailData, 'MNLw0s3jywRA1ySnU' )
                        .then((response) => {
                            console.log('E-mail odeslán:', response);
                            
                            document.getElementById('form').reset();
                            this.vyber.prichut = '';
                            this.vyber.velkost = '';
                        },
                        (error) => {
                            console.log('Chyba při odesílání e-mailu:', error);
                        }
                    );
            }            
        },
        data() {
            return {
                
                num1: Math.floor(Math.random() * 10),
                num2: Math.floor(Math.random() * 10),
                userAnswer: '',
                resultMessage: '',
                vyber: {
                    velkost: '',
                    prichut: '',
                    userEmail: this.userEmail,
                },

            };
        },

    };
</script>

<template>
    <section id="macronConfigurator">
        <!-- button back -->
        <div class="goBack" @click="handleClick">
            <img src="../assets/pictures/goBack.svg" alt="Ísť späť">
        </div>

        <!-- spot with actual choice -->
        <div class="choice-img">
            <img src="../assets/pictures/macron.png" width="100px" alt="Tvoja volba">
        </div>

        <article>
            <!-- heading -->
            <h2>Macron Configurator</h2>
            <p style="padding-top: 0;">Nakonfiguruj si vlastnú veľkosť balenia, príchuť alebo dokonca aj farbu!</p>

            <!-- volba velkosti -->
            <p>Vyber si veľkosť.</p>
            <div class="button-wraper">
                <button 
                    @click="updateVelkost('L')" 
                    :class="{ 'active': vyber.velkost === 'L' }" 
                    class="button small"> 
                    <p> L </p> 
                </button>
                <button 
                    @click="updateVelkost('M')" 
                    :class="{ 'active': vyber.velkost === 'M' }" 
                    class="button small"> 
                    <p> M </p> 
                </button>
                <button 
                    @click="updateVelkost('S')" 
                    :class="{ 'active': vyber.velkost === 'S' }" 
                    class="button small"> 
                    <p> S </p> 
                </button>
                <button 
                    @click="updateVelkost('teaser')" 
                    :class="{ 'active': vyber.velkost === 'teaser' }" 
                    class="button small teaser"> 
                    <p> Teaser </p> 
                </button>

                <p style="padding-top: 0;">Počet kusov v balení: 
                    <b v-if="vyber.velkost === 'L'">30</b> 
                    <b v-if="vyber.velkost === 'M'">20</b> 
                    <b v-if="vyber.velkost === 'S'">10</b> 
                    <b v-if="vyber.velkost === 'teaser'">4</b>
                </p>
            </div>

            <!-- volba prichute -->
            <p>Vyber si nejakú z našich vychytených príchutí.</p>
            <div class="button-wraper">
                <div 
                    @click="updatePrichut('lesnaZmes')"  
                    :class="{ 'active': vyber.prichut === 'lesnaZmes' && vyber.velkost !== 'teaser'}" 
                    class="button big">

                    <!-- button text -->
                    <h6 id="red">ČERVENÁ</h6>
                    <small>Lesná zmes</small>
                </div>

                <div 
                    @click="updatePrichut('kava')" 
                    :class="{ 'active': vyber.prichut === 'kava' && vyber.velkost !== 'teaser'}" 
                    class="button big">

                    <!-- button text -->
                    <h6 id="brown">HNEDÁ</h6>
                    <small>Káva</small>
                </div>

                <div 
                    @click="updatePrichut('karamel')"
                    :class="{ 'active': vyber.prichut === 'karamel' && vyber.velkost !== 'teaser'}"  
                    class="button big">

                    <!-- button text -->
                    <h6 id="white">BIELA</h6>
                    <small>Karamel</small>
                </div>

                <div 
                    @click="updatePrichut('pistacie')" 
                    :class="{ 'active': vyber.prichut === 'pistacie' && vyber.velkost !== 'teaser'}" 
                    class="button big">

                    <!-- button text -->
                    <h6 id="green">ZELENÁ</h6>
                    <small>Pistácie</small>
                </div>
            </div>


            <!-- email set -->
            <p>Zadaj mail, v ktorom sa dohodneme na detailoch, zároveň žiadame o vyriešenie jednoduchého príkladu aby sme si overrili, že nie si robot. </p>
            <div class="button-wraper form-wraper">
                <form id="form" @submit.prevent="checkAnswerAndSendEmail">
                    <div class="longer">
                        <input v-model="vyber.userEmail" class="custom-input" type="mail" placeholder="examplemail@gmail.com" required>
                    </div>
                    <div class="shorter">
                        <input class="custom-input2" v-model="userAnswer" type="text" :placeholder="`${num1}+${num2}`">
                    </div>

                    <button type="submit">Poslať!</button>
                </form>
            </div>
            <small v-if="resultMessage">{{ resultMessage }}</small>
            <p>
                Chceš to nakombinovať úple podľa seba? <a href="mailto:dezertnyraj@gmail.com?subject=Your%20Subject&body=Your%20Message">Tu</a> nám napíš svoju predstavu.    
            </p>
        </article>
    </section>

</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    #macronConfigurator{
        width: 100%;
        height: 39.063vw; //235.125rem
        @include flex;
        gap: 4.604vw;
        margin: 0 auto;    
        margin-bottom: 2.083vw; 
        .goBack{
            img{
                width: clamp(2.5rem,2.708vw,6.438rem);
                height: auto;
            }
        }
        article{
            font-family: $charis;
            text-align: justify;
            max-width: 31%;
            align-self: center;
            background-color: $lightGrey;
            padding: 40px;
            p{
                font-size: 0.833vw;
                padding-top: 1.563vw;
                a{
                    color: $black;
                }
            }
            h2{
                font-size: 2.3vw;
                font-family: $heading;
            }
            .button-wraper{
                display: flex;
                justify-content: space-between;
                align-items: center;
                .button{
                    all: unset;
                    @include flex;
                    background-image: url('../assets/pictures/orbBorder.svg');
                    background-repeat: no-repeat;
                    background-size: contain;
                    cursor: pointer;
                    transition: 0.5s;
                    #red{
                        color: $redText;
                    }
                    #brown{
                        color: $brown;
                    }
                    #white{
                        color: $black;
                    }
                    #green{
                        color: $greenText;
                    }
                    &:hover{
                        opacity: 0.6;
                    }
                }
                h6{
                    font-weight: bold;
                    font-size: 0.933vw;
                }
                .small{
                    width: 3.646vw;
                    height: 2.552vw;
                    p{
                        padding-top: 0;
                    }
                }

                .big{
                    width: 6.771vw;
                    height: 4.74vw;
                    flex-direction: column;
                    small{
                        font-size: 0.690vw;
                    }
                }
            }
            .form-wraper{
                form{
                    display: flex;
                    align-items: center;
                    .longer{
                        background-image: url('../assets/pictures/orbBorderLong.svg');
                        background-repeat: no-repeat;
                        background-size: cover; 
                        @include flex;

                        width: 14.583vw;
                        height: 2.5vw;
                        .custom-input{
                            all: unset;
                        }
                    }
                    .shorter{
                        background-image: url('../assets/pictures/orbBorder.svg');
                        background-repeat: no-repeat;
                        background-size: cover; 
                        @include flex;

                        width: 3.802vw;
                        height: 2.76vw;
                        .custom-input2{
                            font-size: 0.733vw !important;
                            all: unset;
                            width: 40%;
                        }
                    }

                    button{
                        all: unset;
                        background-image: url('../assets/pictures/orbBorder.svg');
                        background-repeat: no-repeat;
                        background-size: cover; 
                        @include flex;
                        cursor: pointer;
                        font-size: 0.695vw !important;
                        font-weight: bold;
                        width: 3.802vw;
                        height: 2.76vw;
                        transition: 0.5s;
                        &:hover{
                            opacity: 0.6;
                        }
                    }
                }
            }
        }
        .choice-img{
            display: flex;
            align-items: center;
        }
        @media only screen and (max-width: 1024px){
            flex-direction: column;
            height: 100%;
            article{
                max-width: 80%;
            }
        }

        .active{
            scale: 0.95 !important;
            opacity: 0.5 !important;
        }
    }
</style>