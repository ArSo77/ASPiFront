<template>


    <v-app dark>
        <header></header>



            <!--<img src="http://medicalonline.pl/files_med/606/581/t_39/20090216214059_Logo_as_1male_xl.jpg" height="112" width="316"/>-->




        <v-btn @click="testf">{{test123}}</v-btn>




        <v-container grid-list-md text-xs-center>
            <v-layout row wrap>


                <v-flex xs12>
                    <v-card dark color="gray">
                        <v-card-text class="px-0">
                            <!--<img src="http://medicalonline.pl/files_med/606/581/t_39/20090216214059_Logo_as_1male_xl.jpg" height="112" width="316"/>-->
                            <v-spacer></v-spacer>
                            <h1>Monitor gazów medycznych</h1>
                        </v-card-text>
                    </v-card>
                </v-flex>



                <v-flex v-for="i in 3" :key="`4${i}`" xs6>
                    <v-card dark color="primary">
                        <v-card-text class="px-0">
                            <app-ekrany :wartosciEnable="wartosciEkran" :alarmyEnable="alarmyEkran"></app-ekrany>
                        </v-card-text>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>









            <v-footer :fixed="fixed" app>

                <img src="http://medicalonline.pl/files_med/606/581/t_39/20090216214059_Logo_as_1male_xl.jpg"
                     height="30" width="90"/>
                <v-spacer></v-spacer>
                <v-btn @click="wartosciEkran=!wartosciEkran">Wartości:{{wartosciEkran}}</v-btn>
                <v-btn @click="alarmyEkran=!alarmyEkran">Alarmy:{{alarmyEkran}}</v-btn>

                <span>&copy;2018</span>
                <!--<v-btn>Ustawienia</v-btn>-->
            </v-footer>
    </v-app>
</template>

<script>

    import Ekran from './Components/Ekran'

    export default {

        data() {
            return {
                test123: 41,
                wartosciEkran:true,
                alarmyEkran:true
            }
        },


        components: {
            appEkrany: Ekran
        },

        created: function () {
        },


        methods: {
            testf(){
                this.test123=2;
            }
        }


    }
</script>

<style scoped>
    .redd {
        background-color: red;
    }
</style>