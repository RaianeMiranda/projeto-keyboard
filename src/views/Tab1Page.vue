<template>

  <ion-list>

    <ion-item>
      <ion-label position="floating">Insira seu Nome</ion-label>
      <ion-input tab="tab1" href="keyboardWillShow" keyboardWillShow placeholder="Enter text"></ion-input>
    </ion-item>

    <ion-item>
      <ion-label position="floating">Email</ion-label>
      <ion-input type="email" placeholder="Enter text"></ion-input>
    </ion-item>

    <ion-item>
      <ion-label position="floating">Senha</ion-label>
      <ion-input type="password" placeholder="Enter text"></ion-input>
    </ion-item>

  </ion-list>
  <ion-button shape="round">Round</ion-button>



</template>


<script lang="ts">
import { IonInput, IonItem, IonLabel, IonList, IonButton } from '@ionic/vue';
import { Keyboard } from '@capacitor/keyboard';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { IonInput, IonItem, IonLabel, IonList, IonButton },
  ionicViewDidEnter() {
    Keyboard.addListener('keyboardWillShow', info => {
      console.log('keyboard will show with height:', info.keyboardHeight);
    });

    Keyboard.addListener('keyboardDidShow', info => {
      console.log('keyboard did show with height:', info.keyboardHeight);
    });

    Keyboard.addListener('keyboardWillHide', () => {
      console.log('keyboard will hide');
    });

    Keyboard.addListener('keyboardDidHide', () => {
      console.log('keyboard did hide');
    });
  }
});







</script>