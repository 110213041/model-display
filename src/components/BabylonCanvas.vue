<script lang="ts" setup>
import { ref, useTemplateRef, onMounted } from "vue"
import { AppendSceneAsync, ArcRotateCamera, Engine, Scene } from "@babylonjs/core"
import {registerBuiltInLoaders } from "@babylonjs/loaders/dynamic"

import donut1 from "../assets/donut1.glb?url"

const bjsCanvas = useTemplateRef("bjsCanvas");
registerBuiltInLoaders();

const modelSelect = ref(donut1)

onMounted(async () => {
    await createScene(bjsCanvas.value!);
})


async function createScene(canvas: HTMLCanvasElement) {
    const engine = new Engine(canvas);
    const scene = new Scene(engine);
    
    await AppendSceneAsync(modelSelect.value, scene);

    scene.createDefaultCameraOrLight(true, true, true);
    const camera = scene.activeCamera as ArcRotateCamera;
    camera.alpha = Math.PI / 2;

    engine.runRenderLoop(()=>{
        scene.render();
    });
}


</script>

<template>
    <canvas ref="bjsCanvas" width="500" height="500" />
</template>

<style scoped></style>
