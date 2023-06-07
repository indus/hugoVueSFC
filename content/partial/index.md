{
"title": "Example: Partial - linked assets",
"date": "2023-06-04",
"description": "This example uses partials in a template. The style and script assets are linked. The script asset uses a global version of the Vue library. The template asset is rendered in the div#sfc element directly.",
"tags": ["example", "partial"],
"hideSummary": true,
"vueGlobal": true,
"vueSFC": "msg_partial.vue"
}



### Code used for this page:
#### [extend_head.html](https://github.com/indus/hugoVueSFC/blob/main/layouts/partials/extend_head.html#L7):
``` hbs {lineNos=true,lineNoStart=7}
{{partial "vueSFC/global" (dict "ctx" $)}} 
```
#### [single.html](https://github.com/indus/hugoVueSFC/blob/main/layouts/_default/single.html#L35):
``` hbs {lineNos=true,lineNoStart=35}
{{partial "vueSFC/all" (dict "ctx" $ "path" .Params.vueSFC  "mountId" "sfc" "defer" true ) }}
```
<small>🤓 To gain more control you may want to use the following equivalent:</small>
``` hbs {lineNos=true}
{{partial "vueSFC/style" (dict "ctx" $ "path" .Params.vueSFC) }}
<div id="sfc">
  {{partial "vueSFC/template" (dict "ctx" $ "path" .Params.vueSFC)}}
</div>
{{partial "vueSFC/script" (dict "ctx" $ "path" .Params.vueSFC "defer" true)}}
```

#### [msg_partial.vue](https://github.com/indus/hugoVueSFC/blob/main/content/partial/msg_partial.vue):
{{< highlightFile path="msg_partial.vue" lang="vue" options="lineNos=true" >}}