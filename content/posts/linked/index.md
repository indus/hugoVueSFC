{
"title": "Example: Shortcode - linked assets",
"date": "2023-06-04",
"description": "This example uses shortcodes in a post. The style and script assets are linked. The script asset uses a global version of the Ve library. The template asset is rendered in a x-template script that gets used by the vue component.",
"tags": ["example", "linked"],
"hideSummary": true
}

###  Demo:
{{< vueSFC/style path="msg_linked.vue" >}}
<div id="sfc"></div>
{{< vueSFC/template path="msg_linked.vue" xtemplate="msg_tmpl" >}}
{{< vueSFC/script path="msg_linked.vue" >}}

### Code used in this post:
#### Partial:
``` hbs
{{partial "vueSFC/global" (dict "ctx" $)}} 
```
#### Shortcode:
``` hbs
{{</* vueSFC/style path="msg_linked.vue" */>}}
<div id="sfc"></div>
{{</* vueSFC/template path="msg_linked.vue" xtemplate="geetings_tmpl" */>}}
{{</* vueSFC/script path="msg_linked.vue" */>}}
```
#### msg_linked.vue:
``` vue
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
    setup: () => {
    const msg = ref('Hello from Vue!');
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
```

