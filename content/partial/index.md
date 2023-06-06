{
"title": "Example: Partial - linked assets",
"date": "2023-06-04",
"description": "This example uses partials in a template. The style and script assets are linked. The script asset uses a global version of the Vue library. The template asset is rendered in the div#sfc element directly.",
"tags": ["example", "partial"],
"hideSummary": true,
"vueSFC": "msg_partial.vue"
}



### Code used in this post:
#### Partial:
``` hbs
{{partial "vueSFC/global" (dict "ctx" $)}} 
```
``` hbs
{{partial "vueSFC/style" (dict "ctx" $ "path" .Params.vueSFC) }}
<div id="sfc">
  {{partial "vueSFC/template" (dict "ctx" $ "path" .Params.vueSFC)}}
</div>
{{partial "vueSFC/script" (dict "ctx" $ "path" .Params.vueSFC "defer" true)}}
```
#### msg_partial.vue:
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
  color: lighten(limegreen, 5);
  font-weight: bold;
  font-size: 2.5em;
}
</style>
```


