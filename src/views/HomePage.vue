<template>
  <ion-page>
    <!-- <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Calculator </ion-title>
      </ion-toolbar>
    </ion-header> -->

    <ion-content :fullscreen="true">
      <inputField :Input=this.input></inputField>
      <div class="Row">
        <IonButton :number=7 @click="changeInput(7)"></IonButton>
        <IonButton :number=8 @click="changeInput(8)"></IonButton>
        <IonButton :number=9 @click="changeInput(9)"></IonButton>
        <AccButton acc="*" @click="changeOperator('*')"></AccButton>
      </div>
      <div class="Row">
        <IonButton :number=4 @click="changeInput(4)"></IonButton>
        <IonButton :number=5 @click="changeInput(5)"></IonButton>
        <IonButton :number=6 @click="changeInput(6)"></IonButton>
        <AccButton acc="+" @click="changeOperator('+')"></AccButton>
      </div>
      <div class="Row">
        <IonButton :number=1 @click="changeInput(1)"></IonButton>
        <IonButton :number=2 @click="changeInput(2)"></IonButton>
        <IonButton :number=3 @click="changeInput(3)"></IonButton>
        <AccButton acc="-" @click="changeOperator('-')"></AccButton>
      </div>
      <div class="Row">
        <IonButton :number=0 @click="changeInput(0)"></IonButton>
        <AccButton acc="/" @click="changeOperator('/')"></AccButton>
        <AccButton acc="=" @click="calculate()"></AccButton>
        <AccButton acc="C" @click="clearInput()"></AccButton>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import IonButton from '../components/NumberButton.vue';
import AccButton from '../components/AccButton.vue';
import inputField from '../components/InputField.vue';
</script>

<script>
export default {
  data() {
    return {
      input: "",
      numberTyped1: null,
      numberTyped2: null,
      operator: null,
      output: null
    }
  },
  methods: {
    changeInput(numberTyped) {
      if (this.numberTyped1 != null) {
        this.numberTyped2 = numberTyped;
        console.log(this.numberTyped2)
        return;
      } else
        this.numberTyped1 = numberTyped;
      console.log(this.numberTyped1)
      return;
    },
    changeOperator(operatorTyped) {
      switch (operatorTyped) {
        case "*":
          this.operator = operatorTyped
          break;
        case "+":
          this.operator = operatorTyped
          break;
        case "-":
          this.operator = operatorTyped
          break;
        case "/":
          this.operator = operatorTyped
          break;
      }
    },
    calculate() {
      switch (this.operator) {
        case "*":
          this.output = this.numberTyped1 *= this.numberTyped2;
          this.input = this.output.toString();
          console.log(this.output)
          this.clearInput()
          break;
        case "+":
          this.output = this.numberTyped1 + this.numberTyped2;
          this.input = this.output.toString();
          console.log(this.output)
          this.clearInput()
          break;
        case "-":
          this.output = this.numberTyped1 - this.numberTyped2;
          this.input = this.output.toString();
          console.log(this.output)
          this.clearInput()
          break;
        case "/":
          this.output = this.numberTyped1 / this.numberTyped2;
          this.input = this.output.toString();
          console.log(this.output)
          this.clearInput()
          break;
      }
    },
    clearInput() {
      this.numberTyped1 = null
      this.numberTyped2 = null
      this.operator = null
      this.input = ""
    }
  }
}
</script>

<style scoped>
#container {
  text-align: center;

  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;

  color: #8c8c8c;

  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
