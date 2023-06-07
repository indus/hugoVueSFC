{
"title": "Example: Shortcode - inlined assets",
"date": "2023-06-04",
"description": "This example uses shortcodes in a post. The style and script assets are inlined. The script asset includes its own version of the Vue library. The template asset is rendered in the div#sfc element directly.",
"tags": ["example", "inline"],
"hideSummary": true
}

###  Demo:
{{< vueSFC/all path="msg_inline.vue" mountId="sfc" inlineStyle=true inlineScript=true >}}

### Code used in this post:
#### [index.md](https://github.com/indus/hugoVueSFC/blob/main/content/posts/inline/index.md?plain=1#L10):
``` hbs {lineNos=true,lineNoStart=10}
{{</* vueSFC/all path="msg_inline.vue" mountId="sfc" inlineStyle=true inlineScript=true */>}}
```
<small>🤓 To gain more control you may want to use the following equivalent:</small>
``` hbs {lineNos=true}
{{</* vueSFC/style path="msg_inline.vue" inline=true */>}}
<div id="sfc">
{{</* vueSFC/template path="msg_inline.vue" */>}}
</div>
{{</* vueSFC/script path="msg_inline.vue" inline=true */>}}
```

#### [msg_inline.vue](https://github.com/indus/hugoVueSFC/blob/main/content/posts/inline/msg_inline.vue):
{{< highlightFile path="msg_inline.vue" lang="vue" options="lineNos=true" >}}

