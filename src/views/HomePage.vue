<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="dark">
        <ion-title> Calculator </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <div class="calculator">
        <section class="outcome-section">
          <inputField :Input=this.input></inputField>
        </section>
        <section class="button-fields">
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
            <AccButton acc="C" @click="clearAll()" color="medium"></AccButton>
          </div>
        </section>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import IonButton from '../components/NumberButton.vue';
import AccButton from '../components/AccButton.vue';
import inputField from '../components/InputField.vue';
</script >

<script>
export default {
  components: { IonHeader, IonTitle, IonToolbar },
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
      // check if input 1 already exist
      if (this.numberTyped1 != null) {
        // if so, then give input 2 the number
        this.numberTyped2 = numberTyped;
        return;
      } else
        // if not then give input 1 the number
        this.numberTyped1 = numberTyped;
      return;
    },
    changeOperator(operatorTyped) {
      // check which operator is used
      switch (operatorTyped) {
        // change the operator value to the operator input
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
      // calculate, depending on which operator has been used
      switch (this.operator) {
        case "*":
          this.output = this.numberTyped1 *= this.numberTyped2;
          // change the outcome field
          this.input = this.output.toString();
          this.clearInput()
          break;
        case "+":
          this.output = this.numberTyped1 + this.numberTyped2;
          // change the outcome field
          this.input = this.output;
          this.clearInput()
          break;
        case "-":
          this.output = this.numberTyped1 - this.numberTyped2;
          // change the outcome field
          this.input = this.output;
          this.clearInput()
          break;
        case "/":
          this.output = this.numberTyped1 / this.numberTyped2;
          // change the outcome field
          this.input = this.output;
          this.clearInput()
          break;
      }
    },
    clearInput() {
      // clear the input
      this.numberTyped1 = null
      this.numberTyped2 = null
      this.operator = null
    },
    clearAll() {
      // clear everything
      this.numberTyped1 = null
      this.numberTyped2 = null
      this.operator = null
      this.input = 0
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

.calculator {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  background-color: black;
}

.outcome-section {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 50px;
}

.button-fields {
  margin-top: 50px;
}

.Row {
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>
