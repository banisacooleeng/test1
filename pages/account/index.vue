<template>
<div>
    <h1 class="coleen">Coleen</h1>
    <nuxt-link to="/">Coleen Home</nuxt-link>
</div>
  
</template>

<script>

import firebase from 'firebase/app';
import 'firebase/auth';

export default {

    data() {
        return {
            name: '',
            email: '',
        }
    },

    methods: {
        addNumber() {
          const a = 1;
          const b =2;

        }
    },

    created() {
        firebase.auth().onAuthStateChanged(user => {
            if (user) {
                console.log('Naay user')
            } else {
                window.location.href = window.origin;
            }
        })
    },

    beforeCreate() {
        var firebaseConfig = {
            apiKey: "AIzaSyCqDp-CehGc1ZAZhq-de2CXiH99ZUL-FEk",
            authDomain: "testprop-393f6.firebaseapp.com",
            databaseURL: "https://testprop-393f6.firebaseio.com",
            projectId: "testprop-393f6",
            storageBucket: "testprop-393f6.appspot.com",
            messagingSenderId: "566374086267",
            appId: "1:566374086267:web:7447317dcdd9d58296d4de",
            measurementId: "G-WNRZ5PQJXB"
        };
  // Initialize Firebase

        if(firebase.apps.length === 0) {
                firebase.initializeApp(firebaseConfig);
        }
    }

}
</script>

<style>
.coleen {
    font-size: 50px
}
</style>