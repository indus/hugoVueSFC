{
"title": "Example: Shortcode - linked assets",
"date": "2023-06-04",
"description": "This example uses shortcodes in a post. The style and script assets are linked. The script asset uses a global version of the Vue library. The template asset is rendered in a x-template script that gets used by the vue component.",
"tags": ["example", "linked"],
"hideSummary": true
}

###  Demo:
{{< vueSFC/style path="msg_linked.vue" >}}
<div id="sfc"></div>
{{< vueSFC/template path="msg_linked.vue" xtemplate="msg_tmpl" >}}
{{< vueSFC/script path="msg_linked.vue" >}}

### Code used in this post:
#### [Partial](https://github.com/indus/hugoVueSFC/blob/main/layouts/partials/extend_head.html#L6):
``` hbs
{{partial "vueSFC/global" (dict "ctx" $)}} 
```
#### [Shortcode](https://github.com/indus/hugoVueSFC/blob/main/content/posts/linked/index.md?plain=1#L10-L13):
``` hbs
{{</* vueSFC/style path="msg_linked.vue" */>}}
<div id="sfc"></div>
{{</* vueSFC/template path="msg_linked.vue" xtemplate="msg_tmpl" */>}}
{{</* vueSFC/script path="msg_linked.vue" */>}}
```
#### [msg_linked.vue](https://github.com/indus/hugoVueSFC/blob/main/content/posts/linked/msg_linked.vue):
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
    template: "#msg_tmpl",
    setup: () => {
        const msg = ref('Hello from Vue!');
        return { msg };
    }
}).mount("#sfc");
</script>

<style lang="scss">
.msg {
    color: lighten(steelblue, 5);
    font-weight: bold;
    font-size: 2.5em;
}
</style>
```


