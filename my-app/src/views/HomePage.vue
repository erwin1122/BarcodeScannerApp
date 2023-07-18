<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title class="ion-text-center">Barcode Scanner</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <div id="container">
        <h2 class="ion-text-center">Recent Scans</h2>
        <table>
          <thead>
            <tr>
              <th>Value</th>
              <th>Type</th>
              <th>Format</th>
              <th>Options</th>
            </tr>
          </thead>
          <tbody>
            <!-- Hier können Sie Ihre Scan-Daten einfügen. Jeder Datensatz sollte als neuer <tr> eingefügt werden -->
          </tbody>
        </table>
      </div>
      <div id="bottom">
        <ion-button expand="full">Scan</ion-button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton } from '@ionic/vue';
</script>



<style scoped>
#container {
  padding: 15px;
}

#container h2 {
  font-size: 24px;
  margin-bottom: 15px;
}

#container table {
  /* Hier können Sie Ihr Tabelle-Styling hinzufügen */
  width: 100%;
  border: 1px solid #ddd;
  border-collapse: collapse;
}

#container table th, #container table td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}

#bottom {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 15px;
}
</style>
