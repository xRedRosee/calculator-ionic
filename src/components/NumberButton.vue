<template>
    <ion-button shape="round">
        <p> {{ number }}</p>
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