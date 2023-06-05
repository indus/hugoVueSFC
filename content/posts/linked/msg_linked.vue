<template>
  <p class="msg">{{ msg }}</p>
</template>

<script lang="ts">
import type Vue from 'vue'
declare global {
    interface Window { Vue: typeof Vue; }
}
const { createApp, ref } = window.Vue;

createApp({
    template:"#msg_tmpl",
    setup: () => {
    const msg = ref('Hello from Vue!');
    console.info(msg.value);
    return { msg };
    }
}).mount("#sfc");
</script>

<style lang="scss">
.msg {
    color:  lighten(steelblue, 5);
    font-weight: bold;
    font-size: 2.5em;
}
</style>