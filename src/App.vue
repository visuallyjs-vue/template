<script setup>

import renderOptions from "./render-options.ts"
import viewOptions from "./view-options.ts"
import modelOptions from "./model-options.ts"

import greetings from "./greetings.ts"
import CurrentZoom from "./CurrentZoom.vue";
</script>

<template>
  <SurfaceProvider>
    <PaletteComponent class="vjs-demo-palette" selector="[data-vjs-type]">
      <CurrentZoom/>
      <div v-for="g in greetings" data-vjs-type="hello" :data-vjs-label="g.h" class="vjs-hello" :data-vjs-lang="g.lang">{{ g.h }}</div>
      <div v-for="g in greetings" data-vjs-type="world" :data-vjs-label="g.w" class="vjs-world" :data-vjs-lang="g.lang">{{ g.w }}</div>
    </PaletteComponent>
    <SurfaceComponent class="canvas" :renderOptions="renderOptions" :viewOptions="viewOptions" :modelOptions="modelOptions" url="/dataset.json">
      <ControlsComponent/>
      <MiniviewComponent/>
    </SurfaceComponent>
  </SurfaceProvider>
</template>

