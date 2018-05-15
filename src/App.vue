<template>
    <v-layout column align-center>
    <v-btn color="blue" @click="jso">JSON</v-btn>
        <v-btn color="blue" @click="war1=1">clear</v-btn>






    <img src="http://medicalonline.pl/files_med/606/581/t_39/20090216214059_Logo_as_1male_xl.jpg" height="112" width="316"/>




Alarmy:
        <ul>
            <li v-for="alarm in alarmy">
                {{alarm}}
            </li>
        </ul>
Odczyty:
        <ul>
            <li v-for="odczyt in odczyty">
                {{odczyt}}
            </li>
        </ul>
Rodzaje:
        <ul>
            <li v-for="rodzaj in rodzaje">
                {{rodzaj}}
            </li>
        </ul>

<p4>Specialny kod: {{kod}}</p4>
        <p4>Ilość gazów: {{iloscgazow}}</p4>



        <v-footer :fixed="fixed" app>
            <span>&copy;2018</span>
        </v-footer>
        </v-layout>
</template>

<script>

    import TekstJson from './logij.json';


    export default {
        data() {
            return {
                war1:0,

                kod:0,
                iloscgazow:0,

                alarmy:[],
                odczyty:[],
                rodzaje:[]

            }
        },
        created: function(){


            this.kod=TekstJson["0x0"]["holding-registers"][13];
            this.iloscgazow=TekstJson["0x0"]["holding-registers"][14];

            var i=0;
            for(i=0;i<6;i++){
                this.alarmy[i]=TekstJson["0x0"]["holding-registers"][i+1];
            }

            for(i=0;i<6;i++){
                this.odczyty[i]=TekstJson["0x0"]["holding-registers"][i+7];
            }

            for(i=0;i<6;i++){
                this.rodzaje[i]=TekstJson["0x0"]["holding-registers"][i+15];
            }




        },



        methods: {
            jso() {





            }
        }
    }
</script>
