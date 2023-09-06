<template>
    <ion-button shape="round" class="btn" color="dark" size="large">
        <p class="operator"> {{ acc }}</p>
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

<style>
.btn {
    width: 80px;
    height: 80px;
}

.operator {
    font-size: 30px;
}
</style>