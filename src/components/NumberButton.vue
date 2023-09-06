<template>
    <ion-button shape="round" class="btn" color="primary" size="large">
        <p class="number"> {{ number }} </p>
    </ion-button>
</template>

<script>
import { IonButton } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
    components: { IonButton },
    props: {
        number: Number,
    }
});
</script>

<style>
.btn {
    width: 80px;
    height: 80px;
}

.number {
    font-size: 30px;
}
</style>