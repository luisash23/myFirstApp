<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Game List</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Game List</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-list>
        <ion-item v-for="game in games" :key="game.id" @click="goToDetail(game.id)">
          <ion-label>{{ game.name }}</ion-label>
        </ion-item>
      </ion-list>

    </ion-content>
  </ion-page>
</template>
<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonList, IonItem, IonLabel } from '@ionic/vue';
import { useRouter } from 'vue-router';


const router = useRouter();


const games = [
  { id: 'pokemon', name: 'Pokemon' },
  { id: 'megaman', name: 'Mega Man ' },
  { id: 'zelda', name: 'The Legend of Zelda' },
  { id: 'pac-man', name: 'Pac-Man' },
  { id: 'super-mario', name: 'Super Mario' }
];


const goToDetail = (gameId: string) => {

  router.push(`/tabs/detail/${gameId}`);
};
</script>
