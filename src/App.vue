<template>
    <v-layout column align-center>
    <v-btn color="blue" @click="jso">JSON</v-btn>
        <v-btn color="blue" @click="war1=1">clear</v-btn>


        <p1>{{war1}}</p1>

        <v-alert value="true" type="error">
            This is a error alert.
        </v-alert>


        <v-footer :fixed="fixed" app>
            <span>&copy;2018</span>
        </v-footer>
        </v-layout>
</template>

<script>

    import TekstJson from './lj.json';


    export default {
        data() {
            return {
                war1:0
            }
        },
        methods: {
            jso() {

                // console.log(this.test2[0]["0x0"]["holding-registers"]);
                console.log(TekstJson["0x0"]["holding-registers"][1]);
                this.war1 = TekstJson["0x0"]["holding-registers"][1];
                // console.log("test");
                // console.log(TekstJson);
                // console.log("parseon");
                // this.obj = JSON.stringify(TekstJson);
                // console.log(this.obj);


            }
        }
    }
</script>
