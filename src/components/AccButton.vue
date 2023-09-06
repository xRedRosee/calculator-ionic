<template>
    <ion-button shape="round">
        <p> {{ acc }}</p>
    </ion-button>
</template>

<script>
import { IonButton } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
    components: { IonButton },
    name: "AccButton",
    props: {
        acc: Symbol,
    }
});
</script>