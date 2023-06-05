{
"title": "Example: Shortcode - inlined assets",
"date": "2023-06-04",
"description": "This example uses shortcodes in a post. The style and script assets are inlined. The script asset includes its own version of the Vue library. The template asset is rendered in the div#sfc element directly.",
"tags": ["example", "inline"],
"hideSummary": true
}

###  Demo:
{{< vueSFC/style path="msg_inline.vue" inline=true >}}
<div id="sfc">
{{< vueSFC/template path="msg_inline.vue" >}}
</div>
{{< vueSFC/script path="msg_inline.vue" inline=true >}}

### Code used in this post:
#### Shortcode:
``` hbs
{{</* vueSFC/style path="msg_inline.vue" inline=true */>}}
<div id="sfc">
{{</* vueSFC/template path="msg_inline.vue" */>}}
</div>
{{</* vueSFC/script path="msg_inline.vue" inline=true */>}}
```
#### msg_inline.vue:
``` vue
<template>
    <p class="msg">{{ msg }}</p>
</template>

<script lang="ts">
import { createApp, ref } from 'vue/dist/vue.esm-bundler.js';

createApp({
    setup: () => {
    const msg = ref('Hello from Vue!');
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
```


