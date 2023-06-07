{
"title": "Example: Shortcode - linked assets",
"date": "2023-06-04",
"description": "This example uses shortcodes in a post. The style and script assets are linked. The script asset uses a global version of the Vue library. The template asset is rendered in a x-template script that gets used by the vue component.",
"tags": ["example", "linked"],
"hideSummary": true,
"vueGlobal":true
}

###  Demo:
{{< vueSFC/all path="msg_linked.vue" mountId="sfc" xtemplate="msg_tmpl" >}}

### Code used in this post:
#### [extend_head.html](https://github.com/indus/hugoVueSFC/blob/main/layouts/partials/extend_head.html#L7):
``` hbs {lineNos=true,lineNoStart=7}
{{partial "vueSFC/global" (dict "ctx" $)}} 
```
#### [index.md](https://github.com/indus/hugoVueSFC/blob/main/content/posts/linked/index.md?plain=1#L11):
``` hbs {lineNos=true,lineNoStart=11}
{{</* vueSFC/all path="msg_linked.vue" mountId="sfc" xtemplate="msg_tmpl" */>}}
```

<small>🤓 To gain more control you may want to use the following equivalent:</small>
``` hbs {lineNos=true}
{{</* vueSFC/style path="msg_linked.vue" */>}}
<div id="sfc"></div>
{{</* vueSFC/template path="msg_linked.vue" xtemplate="msg_tmpl" */>}}
{{</* vueSFC/script path="msg_linked.vue" */>}}
```
#### [msg_linked.vue](https://github.com/indus/hugoVueSFC/blob/main/content/posts/linked/msg_linked.vue):
{{< highlightFile path="msg_linked.vue" lang="vue" options="lineNos=true" >}}