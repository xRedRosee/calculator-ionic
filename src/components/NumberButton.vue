<template>
    <ion-button shape="round" class="btn">
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
    width: 90px;
    height: 90px;
}

.number {
    font-size: 30px;
}
</style>