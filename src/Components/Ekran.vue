<template>
    <v-layout column align-center>
<h3>
Oddział: Pnumologia<v-spacer></v-spacer>
        Pokój:421
</h3>

        <v-container grid-list-md text-xs-center>
            <v-layout row wrap>

                <v-flex v-for="i in 6" :key="`4${i}`" xs4>
                    <v-card dark :color="kolorki[rodzaje[i-1]]">
                        <v-card-text class="px-0">

                            <div v-if="symboleEnable">
                                <h2> {{symbole[rodzaje[i-1]]}}</h2>
                            </div>

                            <div v-if="!symboleEnable">
                                <h4> {{nazwaGazu[rodzaje[i-1]]}}</h4>
                            </div>






                            <hr>
                            <v-spacer></v-spacer>
                            <div v-if="wartosciEnable">
                            <h4>Wartość:</h4><h3>{{odczyty[i-1]}}</h3>
                                <hr>
                            </div>

                            <div v-if="!alarmyEnable">
                                <h4> {{nazwaAlarmu[alarmy[i-1]]}} </h4>
                            </div>

                        </v-card-text>

                        <div v-if="alarmyEnable">
                        <v-alert :value="true" :type="nazwaAlertu[alarmy[i-1]]">
                            <h4> {{nazwaAlarmu[alarmy[i-1]]}} </h4>
                        </v-alert>
                        </div>

                    </v-card>

                </v-flex>

            </v-layout>
        </v-container>





        <v-footer :fixed="fixed" app>
            <span>&copy;2018</span>
        </v-footer>
    </v-layout>
</template>

<script>

    import TekstJson from '../logij.json';


    export default {
        data() {
            return {
                war1:0,
                kod:0,
                iloscgazow:0,
                alarmy:[],
                odczyty:[],
                rodzaje:[],
                kolorki: ['brak','cyan darken-1','green lighten-2','amber lighten-2','brown lighten-2','blue-grey lighten-3','blue-grey lighten-2'],
                //Kody kolorów! https://vuetifyjs.com/en/style/colors#javascript-color-pack
                nazwaGazu:['brak','Tlen','Podtlenek azotu','Próźnia','Dwutlenek węgla','Spręzone 5Bar','Spręzone 8Bar'],
                nazwaAlarmu:['brak','Norma','Niskie','Wysokie','Zawór','AWARIA'],
                nazwaAlertu:['success','success','warning','warning','warning',"error"],
                symbole:['brak','O2','N20','VAC','CO2','A5','A8']
            }
        },
        props:{
          wartosciEnable: Boolean,
          alarmyEnable: Boolean,
            symboleEnable: Boolean
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

<style lang="stylus">
    $color-pack = false

    @import '~vuetify/src/stylus/main'
</style>