<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>List item</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">List Item</ion-title>
                </ion-toolbar>
            </ion-header>
            <ReusableComponent name="List Item" />       
        </ion-content>
    </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, } from '@ionic/vue';
import ReusableComponent from '@/components/ReusableComponent.vue';
</script>