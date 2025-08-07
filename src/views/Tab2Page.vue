<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>My Profile</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large"></ion-title>
        </ion-toolbar>
      </ion-header>
<ion-card>
<ion-card>
    <img alt="" src="/megacoann.jpg" class="img-property" />
    <ion-card-header>
      <ion-card-title>Luis Saputra P.T</ion-card-title>
      <ion-card-subtitle>XI PPLG 1</ion-card-subtitle>
    </ion-card-header>

    <ion-card-content>
     Here My profile
      <ion-item>
        <ion-label position="stacked">NISN</ion-label>
        <ion-label position="stacked">0098081371</ion-label>
      </ion-item>
      <ion-item>
        <ion-label position="stacked">NO HP</ion-label>
        <ion-label position="stacked">085117012455</ion-label>
      </ion-item>
      <ion-item>
        <ion-label position="stacked">Hobi</ion-label>
        <ion-label position="stacked">Belajar hal baru dan bermain game</ion-label>
      </ion-item>
    </ion-card-content>
  </ion-card>
  </ion-card>
  
      <ExploreContainer name="" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';


</script>
