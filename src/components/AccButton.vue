<template>
    <ion-button shape="round" class="btn">
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
    width: 90px;
    height: 90px;
}

.operator {
    font-size: 30px;
}
</style>