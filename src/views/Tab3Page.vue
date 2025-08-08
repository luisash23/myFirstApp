<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Personal</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Login</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-list>
        <ion-item>
          <ion-input label="username" placeholder="enter your username"  v-model="fullname"></ion-input>
        </ion-item>
        <ion-item>
          <ion-input label="Password" placeholder="enter your password" type="password" v-model="password"></ion-input>
          <ion-input-password-toggle></ion-input-password-toggle>
        </ion-item>
        <ion-button expand="block" color="primary" class="ion-margin-top" @click="submitForm">
          Login
        </ion-button>
      </ion-list>
      
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonActionSheet, IonButton, IonInput } from '@ionic/vue';
const password = ref('');
const fullname = ref('');
const submitForm = () => {
  console.log('Email saya adalah:', fullname.value);
  console.log('Password saya adalah:', password.value);
};
</script>
