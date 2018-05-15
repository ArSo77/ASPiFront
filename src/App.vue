<template>
    <v-layout column align-center>
    <v-btn color="blue" @click="jso">JSON</v-btn>
        <v-btn color="blue" @click="war1=1">clear</v-btn>




<ul>

    <li>
        Alarm1: {{alarm1}}
    </li>

    <li>
        Alarm2: {{alarm2}}
    </li>

    <li>
        Alarm3: {{alarm3}}
    </li>

    <li>
        Alarm4: {{alarm3}}
    </li>

    <li>
        Alarm5: {{alarm3}}
    </li>

    <li>
        Alarm6: {{alarm3}}
    </li>

</ul>

Specialny kod: {{kod}}





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
                alarm1:0,
                alarm2:0,
                alarm3:0,
                alarm4:0,
                alarm5:0,
                alarm6:0,
                odczyt1:0,
                odczyt2:0,
                odczyt3:0,
                odczyt4:0,
                odczyt5:0,
                odczyt6:0,
                kod:0,
                iloscgazow:0,
                rodgaz1:0,
                rodgaz2:0,
                rodgaz3:0,
                rodgaz4:0,
                rodgaz5:0,
                rodgaz6:0,

            }
        },
        created: function(){
            this.alarm1 = TekstJson["0x0"]["holding-registers"][1];
            this.alarm2 = TekstJson["0x0"]["holding-registers"][2];
            this.alarm3 = TekstJson["0x0"]["holding-registers"][3];
            this.alarm4 = TekstJson["0x0"]["holding-registers"][4];
            this.alarm5 = TekstJson["0x0"]["holding-registers"][5];
            this.alarm6 = TekstJson["0x0"]["holding-registers"][6];
            this.odczyt1 = TekstJson["0x0"]["holding-registers"][7];
            this.odczyt2 = TekstJson["0x0"]["holding-registers"][8];
            this.odczyt3 = TekstJson["0x0"]["holding-registers"][9];
            this.odczyt4 = TekstJson["0x0"]["holding-registers"][10];
            this.odczyt5 = TekstJson["0x0"]["holding-registers"][11];
            this.odczyt6 = TekstJson["0x0"]["holding-registers"][12];
            this.kod = TekstJson["0x0"]["holding-registers"][13];
            this.iloscgazow = TekstJson["0x0"]["holding-registers"][14];
            this.rodgaz1 = TekstJson["0x0"]["holding-registers"][15];
            this.rodgaz2 = TekstJson["0x0"]["holding-registers"][16];
            this.rodgaz3 = TekstJson["0x0"]["holding-registers"][17];
            this.rodgaz4 = TekstJson["0x0"]["holding-registers"][18];
            this.rodgaz5 = TekstJson["0x0"]["holding-registers"][19];
            this.rodgaz6 = TekstJson["0x0"]["holding-registers"][20];
        },



        methods: {
            jso() {





            }
        }
    }
</script>
