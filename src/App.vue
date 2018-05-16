<template>



    <v-app dark>
        <!--<img src="http://medicalonline.pl/files_med/606/581/t_39/20090216214059_Logo_as_1male_xl.jpg" height="112" width="316"/>-->

MAIN APK
        {{test}}
        <v-btn @click="test+=1">Dodaj</v-btn>

        <app-ekrany></app-ekrany>
        <app-ekrany></app-ekrany>


        <v-footer :fixed="fixed" app>
            <img src="http://medicalonline.pl/files_med/606/581/t_39/20090216214059_Logo_as_1male_xl.jpg" height="30" width="90"/>
            <v-spacer></v-spacer>
            <span>&copy;2018</span>

        </v-footer>
        </v-layout>
    </v-app>
</template>

<script>

    import Ekran from './Components/Ekran'

    export default {

        data() {
            return {
                test:1,
            }
        },


        components:{
          appEkrany: Ekran
        },

        created: function(){
        },


        methods: {
        }




    }
</script>
