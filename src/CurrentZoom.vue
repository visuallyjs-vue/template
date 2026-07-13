<script setup>
// this component shows how you can use the `useZoom` composable to get access to the current zoom level. Note that this
// component has to be nested inside the `SurfaceProvider` element in App.vue, as SurfaceProvider creates an instance of the
// context from which useZoom can get the current value.
import {useZoom} from "@visuallyjs/browser-ui-vue";
const zoom = useZoom()
</script>
<template>
  Zoom: {{zoom.toFixed(2)}}
</template>
