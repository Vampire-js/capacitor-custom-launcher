<script setup>
 import Main from './components/Main.vue'
import AllApps from './components/AllApps.vue'
import { StatusBar  , Style} from '@capacitor/status-bar'

StatusBar.setOverlaysWebView({ overlay: true });

</script>

<template>
<Main/>

</template>

<style>
 :root{
     --primary:#FF6363;
     --secondary:#FFAB76;
     --tertiary:#FC4F4F;
 }
</style>
