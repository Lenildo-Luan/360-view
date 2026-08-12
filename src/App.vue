<template>
    <div class="view360-wrapper">
        <View360 class="is-16by9" :hotspot="{ zoom: true }" :projection="projection"/>
    </div>
</template>

<script>
import { defineComponent } from "vue";
import { View360, CubemapProjection } from "@egjs/vue3-view360";

export default {
    setup() {
        const projection = new CubemapProjection({
            src: [
                "./posx.jpg",
                "./negx.jpg",
                "./posy.jpg",
                "./negy.jpg",
                "./posz.jpg",
                "./negz.jpg",
            ],
        });

        return {
            projection,
        };
    },
    components: {
        View360,
    },
};
</script>

<style >
.view360-wrapper {
    width: 100vw;
    height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;
}

.view360-container {
    width: 80%;
    /*height: 100%;*/
}

.view360-canvas {
    width: 100%;
    /*height: 100%;*/
}
</style>
