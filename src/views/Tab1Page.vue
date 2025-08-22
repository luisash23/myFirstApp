<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Form</ion-title>
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
          <ion-input label="Nama Panggilan" placeholder="enter your nickname" v-model="nickname"></ion-input>
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


        <ion-list>
          <ion-list-header>
            <ion-label>Makanan Favorit</ion-label>
          </ion-list-header>
          <ion-item v-for="food in foods" :key="food">
            <ion-checkbox :value="food" :checked="favoriteFood.includes(food)" labelPlacement="end"
              @ionChange="toggleFavorite(food, $event)">
              {{ food }}
            </ion-checkbox>
          </ion-item>
        </ion-list>

        <ion-button expand="block" color="primary" class="ion-margin-top" @click="submitForm">
          Submit
        </ion-button>

        <div v-if="submitted" class="result-section ion-padding">
          <h2>Hasil Form</h2>
          <p><strong>Nama Panjang:</strong> {{ name }}</p>
          <p><strong>Nama Panggilan:</strong> {{ nickname }}</p>
          <p><strong>Agama:</strong> {{ agama }}</p>
          <p><strong>Jenis Kelamin:</strong> {{ gender }}</p>
          <p><strong>Alamat:</strong> {{ address }}</p>
          <p><strong>Hobby:</strong> {{ hobby }}</p>
          <p><strong>Makanan Favorit:</strong> {{ favoriteFood.join(', ') }}</p>
        </div>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import {
  IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton,
  IonInput, IonItem, IonSelect, IonSelectOption, IonRadioGroup,
  IonRadio, IonLabel, IonList, IonIcon, IonListHeader, IonCheckbox
} from '@ionic/vue';

const name = ref('');
const nickname = ref('');
const agama = ref('');
const gender = ref('');
const address = ref('');
const hobby = ref('');
const favoriteFood = ref<string[]>([]);
const submitted = ref(false);

const foods = ['Nasi Goreng', 'Mie Goreng', 'Ayam Penyet', 'Ayam Caramel', 'Ikan Bakar'];

const toggleFavorite = (food: string, event: any) => {
  if (event.detail.checked) {
    if (!favoriteFood.value.includes(food)) {
      favoriteFood.value.push(food);
    }
  } else {
    favoriteFood.value = favoriteFood.value.filter(f => f !== food);
  }
};

const submitForm = () => {
  submitted.value = true;
  console.log('Nama Panjang:', name.value);
  console.log('Nama Panggilan:', nickname.value);
  console.log('Agama:', agama.value);
  console.log('Jenis Kelamin:', gender.value);
  console.log('Alamat:', address.value);
  console.log('Hobby:', hobby.value);
  console.log('Makanan Favorit:', favoriteFood.value);
};
</script>

<style>
.result-section {
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
