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
>>>>>>> c050898dd1b2876b04a0f2e0b43bf6467ddd84e0
    </ion-content>
  </ion-page>
</template>

<<<<<<< HEAD
<script>
import { IonButton, IonContent, IonHeader, IonIcon, IonItem, IonLabel, IonList, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { camera } from '@capacitor/cores';

export default {
  name: 'Home',
  components: { IonButton, IonContent, IonHeader, IonIcon, IonItem, IonLabel, IonList, IonPage, IonTitle, IonToolbar },
  data() {
    return {
      scans: [],
    };
  },
  methods: {
    async scanQRCode() {
      const image = await camera.getPhoto({
        quality: 90,
        allowEditing: false,
        resultType: 'base64',
      });

      const qrCode = await this.detectQRCode(image.base64String);
      if (qrCode) {
        this.scans.push({
          id: Date.now(),
          value: qrCode.text,
          type: qrCode.type,
          format: qrCode.format,
        });
      }
    },
    async detectQRCode(imageData) {
      // Hier solltest du ein geeignetes QR-Code-Erkennungs-Plugin verwenden.
      // Dieser Code dient nur als Beispiel und erfordert die Verwendung eines tatsächlichen Plugins.

      const qrCodeReader = new ZXing.BrowserQRCodeReader();
      const qrCodeResult = await qrCodeReader.decodeFromBase64(imageData);
      
      return qrCodeResult ? { text: qrCodeResult.text, type: qrCodeResult.type, format: qrCodeResult.format } : null;
    },
  },
};
=======
<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton } from '@ionic/vue';
>>>>>>> c050898dd1b2876b04a0f2e0b43bf6467ddd84e0
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
