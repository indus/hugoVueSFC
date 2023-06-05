<template>
    <p class="msg">{{ msg }}</p>
</template>

<script lang="ts">
import { createApp, ref } from 'vue/dist/vue.esm-bundler.js';

createApp({
    setup: () => {
    const msg = ref('Hello from Vue!');
    console.info(msg.value);
    return { msg };
    }
}).mount("#sfc");
</script>

<style lang="scss">
.msg {
    color: lighten(salmon, 5);
    font-weight: bold;
    font-size: 2.5em;
}
</style>