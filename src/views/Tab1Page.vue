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
          <ion-icon name="home-outline"></ion-icon>
        </ion-toolbar>
      </ion-header>
      <ion-list>
        <ion-item>
          <ion-input label="Nama Panjang" placeholder="enter your Fullname" v-model="name"></ion-input>
        </ion-item>
        <ion-item>
          <ion-input label="nama panggilan" placeholder="enter your nickname" v-model="nickname"></ion-input>
        </ion-item>
        <ion-item>
          <ion-select label="Agama" placeholder="Select One" v-model="agama">
            <ion-select-option value="Islam">Islam</ion-select-option>
            <ion-select-option value="Kristen">Kristen</ion-select-option>
            <ion-select-option value="Katolik">Katolik</ion-select-option>
            <ion-select-option value="Hindu">Hindu</ion-select-option>
            <ion-select-option value="Buddha">Buddha</ion-select-option>
            <ion-select-option value="Konghucu">Konghucu</ion-select-option>
          </ion-select>
        </ion-item>
        <ion-item>
          <ion-select label="Jenis Kelamin" placeholder="Select One" v-model="gender">
            <ion-select-option value="Laki-laki">Laki-laki</ion-select-option>
            <ion-select-option value="Perempuan">Perempuan</ion-select-option>
          </ion-select>
        </ion-item>
        <ion-item>
          <ion-input label="Alamat" placeholder="enter your address" v-model="address"></ion-input>
        </ion-item>
        <ion-radio-group v-model="hobby">
          <ion-list-header>
            <ion-label>Hobby</ion-label>
          </ion-list-header>
          <ion-item>
            <ion-radio value="Bermain Game" labelPlacement="end">Bermain Game</ion-radio>
          </ion-item>
          <ion-item>
            <ion-radio value="Belajar" labelPlacement="end">Belajar</ion-radio>
          </ion-item>
          <ion-item>
            <ion-radio value="Olahraga" labelPlacement="end">Olahraga</ion-radio>
          </ion-item>
          <ion-item>
            <ion-radio value="Membaca" labelPlacement="end">Membaca</ion-radio>
          </ion-item>
          <ion-item>
            <ion-radio value="Menulis" labelPlacement="end">Menulis</ion-radio>
          </ion-item>
        </ion-radio-group>
        <ion-radio-group v-model="favoriteFood">
          <ion-list-header>
            <ion-label>Makanan Favorit</ion-label>
          </ion-list-header>
          <ion-item>
            <ion-checkbox value="Nasi Goreng" labelPlacement="end">Nasi Goreng</ion-checkbox>
          </ion-item>
          <ion-item>
            <ion-checkbox value="Mie Goreng" labelPlacement="end">Mie Goreng</ion-checkbox>
          </ion-item>
          <ion-item>
            <ion-checkbox value="Ayam Penyet" labelPlacement="end">Ayam Penyet</ion-checkbox>
          </ion-item>
        </ion-radio-group>
        <ion-button expand="block" color="primary" class="ion-margin-top" @click="submitForm">
          Submit
        </ion-button>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { 
  IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, 
  IonInput, IonItem, IonSelect, IonSelectOption, IonRadioGroup, 
  IonRadio, IonLabel, IonList, IonIcon, IonListHeader 
} from '@ionic/vue';

const name = ref('');
const nickname = ref('');
const agama = ref('');
const gender = ref('');
const address = ref('');
const hobby = ref('');
const favoriteFood = ref('');

const submitForm = () => {
  console.log('Nama Panjang:', name.value);
  console.log('Nama Panggilan:', nickname.value);
  console.log('Agama:', agama.value);
  console.log('Jenis Kelamin:', gender.value);
  console.log('Alamat:', address.value);
  console.log('Hobby:', hobby.value);
  console.log('Makanan Favorit:', favoriteFood.value);
};
</script>