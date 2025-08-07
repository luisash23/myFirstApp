<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>home</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">home</ion-title>
        </ion-toolbar>
      </ion-header>
       <ion-button class="button alert" @click="setOpen(true)">Click Me For suprise</ion-button>
  <ion-alert 
    :backdrop-dismiss="false"
    :css-class="'my-custom-class'"
    :animated="true"
    :keyboard-close="true"
    :enter-animation="undefined"
    :leave-animation="undefined"
    :mode="'ios'"
    
    :is-open="isOpen"
    header="Peringatan"
    sub-header="Ini adalah peringatan"
    message=" Saya sudah lapar"
    :buttons="alertButtons"
    @didDismiss="setOpen(false)"
  ></ion-alert>
      <ExploreContainer name="This HomePage" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';

   import { ref } from 'vue';
  import { IonAlert, IonButton } from '@ionic/vue';

  const isOpen = ref(false);
  const alertButtons = ['Action'];

  const setOpen = (state: boolean) => {
    isOpen.value = state;
  };
</script>
