# appian-platform-helm-chart
Documentation and detail of appian helm chart





html {overflow-x: initial !important;}
:root { --bg-color: #ffffff; --text-color: #333333; --select-text-bg-color: #B5D6FC; --select-text-font-color: auto; --monospace: "Lucida Console",Consolas,"Courier",monospace; --title-bar-height: 20px; }
.mac-os-11 { --title-bar-height: 28px; }
html { font-size: 14px; background-color: var(--bg-color); color: var(--text-color); font-family: "Helvetica Neue", Helvetica, Arial, "Segoe UI Emoji", "SF Pro", sans-serif; -webkit-font-smoothing: antialiased; }
h1, h2, h3, h4, h5 { white-space: pre-wrap; }
body { margin: 0px; padding: 0px; height: auto; inset: 0px; font-size: 1rem; line-height: 1.42857; overflow-x: hidden; background: inherit; }
iframe { margin: auto; }
a.url { word-break: break-all; }
a:active, a:hover { outline: 0px; }
.in-text-selection, ::selection { text-shadow: none; background: var(--select-text-bg-color); color: var(--select-text-font-color); }
#write { margin: 0px auto; height: auto; width: inherit; word-break: normal; overflow-wrap: break-word; position: relative; white-space: normal; overflow-x: visible; padding-top: 36px; }
#write.first-line-indent p { text-indent: 2em; }
#write.first-line-indent li p, #write.first-line-indent p *, #write.first-line-indent svg * { text-indent: 0px; }
#write.first-line-indent li { margin-left: 2em; }
.for-image #write { padding-left: 8px; padding-right: 8px; }
body.typora-export { padding-left: 30px; padding-right: 30px; }
.typora-export .footnote-line, .typora-export li, .typora-export p { white-space: pre-wrap; }
.typora-export .task-list-item input { pointer-events: none; }
@media screen and (max-width: 500px) {
 body.typora-export { padding-left: 0px; padding-right: 0px; }
 #write { padding-left: 20px; padding-right: 20px; }
}
#write li > figure:last-child { margin-bottom: 0.5rem; }
#write ol, #write ul { position: relative; }
img { max-width: 100%; vertical-align: middle; image-orientation: from-image; }
button, input, select, textarea { color: inherit; font: inherit; }
input[type="checkbox"], input[type="radio"] { line-height: normal; padding: 0px; }
*, ::after, ::before { box-sizing: border-box; }
#write h1, #write h2, #write h3, #write h4, #write h5, #write h6, #write p, #write pre { width: inherit; position: relative; }
#write svg h1, #write svg h2, #write svg h3, #write svg h4, #write svg h5, #write svg h6, #write svg p { position: static; }
svg sub, svg sup { position: static; }
.nodeLabel p { padding-right: 2px; padding-left: 2px; }
.typora-export .nodeLabel p { padding-right: 0px; padding-left: 0px; }
foreignobject { overflow: visible; }
p { line-height: inherit; }
h1, h2, h3, h4, h5, h6 { break-after: avoid-page; break-inside: avoid; orphans: 4; }
p { orphans: 4; }
li p { orphans: 1; }
h1 { font-size: 2rem; }
h2 { font-size: 1.8rem; }
h3 { font-size: 1.6rem; }
h4 { font-size: 1.4rem; }
h5 { font-size: 1.2rem; }
h6 { font-size: 1rem; }
.md-math-block, .md-rawblock, h1, h2, h3, h4, h5, h6, p { margin-top: 1rem; margin-bottom: 1rem; }
.hidden { display: none; }
.md-blockmeta { color: rgb(204, 204, 204); font-weight: 700; font-style: italic; }
a { cursor: pointer; }
sup.md-footnote { padding: 2px 4px; background-color: rgba(238, 238, 238, 0.7); color: rgb(85, 85, 85); border-radius: 4px; cursor: pointer; }
sup.md-footnote a, sup.md-footnote a:hover { color: inherit; text-transform: inherit; text-decoration: inherit; }
#write input[type="checkbox"] { cursor: pointer; width: inherit; height: inherit; }
figure { overflow-x: auto; margin: 1.2em 0px; max-width: calc(100% + 16px); padding: 0px; }
figure > table { margin: 0px; }
thead, tr { break-inside: avoid; break-after: auto; }
thead { display: table-header-group; }
table { border-collapse: collapse; border-spacing: 0px; width: 100%; overflow: auto; break-inside: auto; text-align: left; }
table.md-table td { min-width: 32px; }
.CodeMirror-gutters { border-right: 0px; background-color: inherit; }
.CodeMirror-linenumber { user-select: none; }
.CodeMirror { text-align: left; }
.CodeMirror-placeholder { opacity: 0.3; }
.CodeMirror pre { padding: 0px 4px; }
.CodeMirror-lines { padding: 0px; }
div.hr:focus { cursor: none; }
#write pre { white-space: pre-wrap; }
#write.fences-no-line-wrapping pre { white-space: pre; }
#write pre.ty-contain-cm { white-space: normal; }
.CodeMirror-gutters { margin-right: 4px; }
.md-fences { font-size: 0.9rem; display: block; break-inside: avoid; text-align: left; overflow: visible; white-space: pre; background: inherit; position: relative !important; }
.md-fences-adv-panel { width: 100%; margin-top: 10px; text-align: center; padding-top: 0px; padding-bottom: 8px; overflow-x: auto; }
#write .md-fences.mock-cm { white-space: pre-wrap; }
.md-fences.md-fences-with-lineno { padding-left: 0px; }
#write.fences-no-line-wrapping .md-fences.mock-cm { white-space: pre; overflow-x: auto; }
.md-fences.mock-cm.md-fences-with-lineno { padding-left: 8px; }
.CodeMirror-line, twitterwidget { break-inside: avoid; }
svg { break-inside: avoid; }
.footnotes { opacity: 0.8; font-size: 0.9rem; margin-top: 1em; margin-bottom: 1em; }
.footnotes + .footnotes { margin-top: 0px; }
.md-reset { margin: 0px; padding: 0px; border: 0px; outline: 0px; vertical-align: top; background: 0px 0px; text-decoration: none; text-shadow: none; float: none; position: static; width: auto; height: auto; white-space: nowrap; cursor: inherit; -webkit-tap-highlight-color: transparent; line-height: normal; font-weight: 400; text-align: left; box-sizing: content-box; direction: ltr; }
li div { padding-top: 0px; }
blockquote { margin: 1rem 0px; }
li .mathjax-block, li p { margin: 0.5rem 0px; }
li blockquote { margin: 1rem 0px; }
li { margin: 0px; position: relative; }
blockquote > :last-child { margin-bottom: 0px; }
blockquote > :first-child, li > :first-child { margin-top: 0px; }
.footnotes-area { color: rgb(136, 136, 136); margin-top: 0.714rem; padding-bottom: 0.143rem; white-space: normal; }
#write .footnote-line { white-space: pre-wrap; }
@media print {
 body, html { border: 1px solid transparent; height: 99%; break-after: avoid; break-before: avoid; font-variant-ligatures: no-common-ligatures; }
 #write { margin-top: 0px; border-color: transparent !important; padding-top: 0px !important; padding-bottom: 0px !important; }
 .typora-export * { -webkit-print-color-adjust: exact; }
 .typora-export #write { break-after: avoid; }
 .typora-export #write::after { height: 0px; }
 .is-mac table { break-inside: avoid; }
 #write > p:nth-child(1) { margin-top: 0px; }
 .typora-export-show-outline .typora-export-sidebar { display: none; }
 figure { overflow-x: visible; }
}
.footnote-line { margin-top: 0.714em; font-size: 0.7em; }
a img, img a { cursor: pointer; }
pre.md-meta-block { font-size: 0.8rem; min-height: 0.8rem; white-space: pre-wrap; background: rgb(204, 204, 204); display: block; overflow-x: hidden; }
p > .md-image:only-child:not(.md-img-error) img, p > img:only-child { display: block; margin: auto; }
#write.first-line-indent p > .md-image:only-child:not(.md-img-error) img { left: -2em; position: relative; }
p > .md-image:only-child { display: inline-block; width: 100%; }
#write .MathJax\_Display { margin: 0.8em 0px 0px; }
.md-math-block { width: 100%; }
.md-math-block:not(:empty)::after { display: none; }
.MathJax\_ref { fill: currentcolor; }
[contenteditable="true"]:active, [contenteditable="true"]:focus, [contenteditable="false"]:active, [contenteditable="false"]:focus { outline: 0px; box-shadow: none; }
.md-task-list-item { position: relative; list-style-type: none; }
.task-list-item.md-task-list-item { padding-left: 0px; }
.md-task-list-item > input { position: absolute; top: 0px; left: 0px; margin-left: -1.2em; margin-top: calc(1em - 10px); border: none; }
.math { font-size: 1rem; }
.md-toc { min-height: 3.58rem; position: relative; font-size: 0.9rem; border-radius: 10px; }
.md-toc-content { position: relative; margin-left: 0px; }
.md-toc-content::after, .md-toc::after { display: none; }
.md-toc-item { display: block; color: rgb(65, 131, 196); }
.md-toc-item a { text-decoration: none; }
.md-toc-inner:hover { text-decoration: underline; }
.md-toc-inner { display: inline-block; cursor: pointer; }
.md-toc-h1 .md-toc-inner { margin-left: 0px; font-weight: 700; }
.md-toc-h2 .md-toc-inner { margin-left: 2em; }
.md-toc-h3 .md-toc-inner { margin-left: 4em; }
.md-toc-h4 .md-toc-inner { margin-left: 6em; }
.md-toc-h5 .md-toc-inner { margin-left: 8em; }
.md-toc-h6 .md-toc-inner { margin-left: 10em; }
@media screen and (max-width: 48em) {
 .md-toc-h3 .md-toc-inner { margin-left: 3.5em; }
 .md-toc-h4 .md-toc-inner { margin-left: 5em; }
 .md-toc-h5 .md-toc-inner { margin-left: 6.5em; }
 .md-toc-h6 .md-toc-inner { margin-left: 8em; }
}
a.md-toc-inner { font-size: inherit; font-style: inherit; font-weight: inherit; line-height: inherit; }
.footnote-line a:not(.reversefootnote) { color: inherit; }
.reversefootnote { font-family: ui-monospace, sans-serif; }
.md-attr { display: none; }
.md-fn-count::after { content: "."; }
code, pre, samp, tt { font-family: var(--monospace); }
kbd { margin: 0px 0.1em; padding: 0.1em 0.6em; font-size: 0.8em; color: rgb(36, 39, 41); background: rgb(255, 255, 255); border: 1px solid rgb(173, 179, 185); border-radius: 3px; box-shadow: rgba(12, 13, 14, 0.2) 0px 1px 0px, rgb(255, 255, 255) 0px 0px 0px 2px inset; white-space: nowrap; vertical-align: middle; }
.md-comment { color: rgb(162, 127, 3); opacity: 0.6; font-family: var(--monospace); }
code { text-align: left; vertical-align: initial; }
a.md-print-anchor { white-space: pre !important; border-width: initial !important; border-style: none !important; border-color: initial !important; display: inline-block !important; position: absolute !important; width: 1px !important; right: 0px !important; outline: 0px !important; background: 0px 0px !important; text-decoration: initial !important; text-shadow: initial !important; }
.os-windows.monocolor-emoji .md-emoji { font-family: "Segoe UI Symbol", sans-serif; }
.md-diagram-panel > svg { max-width: 100%; }
[lang="flow"] svg, [lang="mermaid"] svg { max-width: 100%; height: auto; }
[lang="mermaid"] .node text { font-size: 1rem; }
table tr th { border-bottom: 0px; }
video { max-width: 100%; display: block; margin: 0px auto; }
iframe { max-width: 100%; width: 100%; border: none; }
.highlight td, .highlight tr { border: 0px; }
mark { background: rgb(255, 255, 0); color: rgb(0, 0, 0); }
.md-html-inline .md-plain, .md-html-inline strong, mark .md-inline-math, mark strong { color: inherit; }
.md-expand mark .md-meta { opacity: 0.3 !important; }
mark .md-meta { color: rgb(0, 0, 0); }
@media print {
 .typora-export h1, .typora-export h2, .typora-export h3, .typora-export h4, .typora-export h5, .typora-export h6 { break-inside: avoid; }
}
.md-diagram-panel .messageText { stroke: none !important; }
.md-diagram-panel .start-state { fill: var(--node-fill); }
.md-diagram-panel .edgeLabel rect { opacity: 1 !important; }
.md-fences.md-fences-math { font-size: 1em; }
.md-fences-advanced:not(.md-focus) { padding: 0px; white-space: nowrap; border: 0px; }
.md-fences-advanced:not(.md-focus) { background: inherit; }
.mermaid-svg { margin: auto; }
.typora-export-show-outline .typora-export-content { max-width: 1440px; margin: auto; display: flex; flex-direction: row; }
.typora-export-sidebar { width: 300px; font-size: 0.8rem; margin-top: 80px; margin-right: 18px; }
.typora-export-show-outline #write { --webkit-flex: 2; flex: 2 1 0%; }
.typora-export-sidebar .outline-content { position: fixed; top: 0px; max-height: 100%; overflow: hidden auto; padding-bottom: 30px; padding-top: 60px; width: 300px; }
@media screen and (max-width: 1024px) {
 .typora-export-sidebar, .typora-export-sidebar .outline-content { width: 240px; }
}
@media screen and (max-width: 800px) {
 .typora-export-sidebar { display: none; }
}
.outline-content li, .outline-content ul { margin-left: 0px; margin-right: 0px; padding-left: 0px; padding-right: 0px; list-style: none; overflow-wrap: anywhere; }
.outline-content ul { margin-top: 0px; margin-bottom: 0px; }
.outline-content strong { font-weight: 400; }
.outline-expander { width: 1rem; height: 1.42857rem; position: relative; display: table-cell; vertical-align: middle; cursor: pointer; padding-left: 4px; }
.outline-expander::before { content: ""; position: relative; font-family: Ionicons; display: inline-block; font-size: 8px; vertical-align: middle; }
.outline-item { padding-top: 3px; padding-bottom: 3px; cursor: pointer; }
.outline-expander:hover::before { content: ""; }
.outline-h1 > .outline-item { padding-left: 0px; }
.outline-h2 > .outline-item { padding-left: 1em; }
.outline-h3 > .outline-item { padding-left: 2em; }
.outline-h4 > .outline-item { padding-left: 3em; }
.outline-h5 > .outline-item { padding-left: 4em; }
.outline-h6 > .outline-item { padding-left: 5em; }
.outline-label { cursor: pointer; display: table-cell; vertical-align: middle; text-decoration: none; color: inherit; }
.outline-label:hover { text-decoration: underline; }
.outline-item:hover { border-color: rgb(245, 245, 245); background-color: var(--item-hover-bg-color); }
.outline-item:hover { margin-left: -28px; margin-right: -28px; border-left: 28px solid transparent; border-right: 28px solid transparent; }
.outline-item-single .outline-expander::before, .outline-item-single .outline-expander:hover::before { display: none; }
.outline-item-open > .outline-item > .outline-expander::before { content: ""; }
.outline-children { display: none; }
.info-panel-tab-wrapper { display: none; }
.outline-item-open > .outline-children { display: block; }
.typora-export .outline-item { padding-top: 1px; padding-bottom: 1px; }
.typora-export .outline-item:hover { margin-right: -8px; border-right: 8px solid transparent; }
.typora-export .outline-expander::before { content: "+"; font-family: inherit; top: -1px; }
.typora-export .outline-expander:hover::before, .typora-export .outline-item-open > .outline-item > .outline-expander::before { content: "−"; }
.typora-export-collapse-outline .outline-children { display: none; }
.typora-export-collapse-outline .outline-item-open > .outline-children, .typora-export-no-collapse-outline .outline-children { display: block; }
.typora-export-no-collapse-outline .outline-expander::before { content: "" !important; }
.typora-export-show-outline .outline-item-active > .outline-item .outline-label { font-weight: 700; }
.md-inline-math-container mjx-container { zoom: 0.95; }
mjx-container { break-inside: avoid; }
.md-alert.md-alert-note { border-left-color: rgb(9, 105, 218); }
.md-alert.md-alert-important { border-left-color: rgb(130, 80, 223); }
.md-alert.md-alert-warning { border-left-color: rgb(154, 103, 0); }
.md-alert.md-alert-tip { border-left-color: rgb(31, 136, 61); }
.md-alert.md-alert-caution { border-left-color: rgb(207, 34, 46); }
.md-alert { padding: 0px 1em; margin-bottom: 16px; color: inherit; border-left: 0.25em solid rgb(0, 0, 0); }
.md-alert-text-note { color: rgb(9, 105, 218); }
.md-alert-text-important { color: rgb(130, 80, 223); }
.md-alert-text-warning { color: rgb(154, 103, 0); }
.md-alert-text-tip { color: rgb(31, 136, 61); }
.md-alert-text-caution { color: rgb(207, 34, 46); }
.md-alert-text { font-size: 0.9rem; font-weight: 700; }
.md-alert-text svg { fill: currentcolor; position: relative; top: 0.125em; margin-right: 1ch; overflow: visible; }
.md-alert-text-container::after { content: attr(data-text); text-transform: capitalize; pointer-events: none; margin-right: 1ch; }


.CodeMirror { height: auto; }
.CodeMirror.cm-s-inner { background: inherit; }
.CodeMirror-scroll { overflow: auto hidden; z-index: 3; }
.CodeMirror-gutter-filler, .CodeMirror-scrollbar-filler { background-color: rgb(255, 255, 255); }
.CodeMirror-gutters { border-right: 1px solid rgb(221, 221, 221); background: inherit; white-space: nowrap; }
.CodeMirror-linenumber { padding: 0px 3px 0px 5px; text-align: right; color: rgb(153, 153, 153); }
.cm-s-inner .cm-keyword { color: rgb(119, 0, 136); }
.cm-s-inner .cm-atom, .cm-s-inner.cm-atom { color: rgb(34, 17, 153); }
.cm-s-inner .cm-number { color: rgb(17, 102, 68); }
.cm-s-inner .cm-def { color: rgb(0, 0, 255); }
.cm-s-inner .cm-variable { color: rgb(0, 0, 0); }
.cm-s-inner .cm-variable-2 { color: rgb(0, 85, 170); }
.cm-s-inner .cm-variable-3 { color: rgb(0, 136, 85); }
.cm-s-inner .cm-string { color: rgb(170, 17, 17); }
.cm-s-inner .cm-property { color: rgb(0, 0, 0); }
.cm-s-inner .cm-operator { color: rgb(152, 26, 26); }
.cm-s-inner .cm-comment, .cm-s-inner.cm-comment { color: rgb(170, 85, 0); }
.cm-s-inner .cm-string-2 { color: rgb(255, 85, 0); }
.cm-s-inner .cm-meta { color: rgb(85, 85, 85); }
.cm-s-inner .cm-qualifier { color: rgb(85, 85, 85); }
.cm-s-inner .cm-builtin { color: rgb(51, 0, 170); }
.cm-s-inner .cm-bracket { color: rgb(153, 153, 119); }
.cm-s-inner .cm-tag { color: rgb(17, 119, 0); }
.cm-s-inner .cm-attribute { color: rgb(0, 0, 204); }
.cm-s-inner .cm-header, .cm-s-inner.cm-header { color: rgb(0, 0, 255); }
.cm-s-inner .cm-quote, .cm-s-inner.cm-quote { color: rgb(0, 153, 0); }
.cm-s-inner .cm-hr, .cm-s-inner.cm-hr { color: rgb(153, 153, 153); }
.cm-s-inner .cm-link, .cm-s-inner.cm-link { color: rgb(0, 0, 204); }
.cm-negative { color: rgb(221, 68, 68); }
.cm-positive { color: rgb(34, 153, 34); }
.cm-header, .cm-strong { font-weight: 700; }
.cm-del { text-decoration: line-through; }
.cm-em { font-style: italic; }
.cm-link { text-decoration: underline; }
.cm-error { color: red; }
.cm-invalidchar { color: red; }
.cm-constant { color: rgb(38, 139, 210); }
.cm-defined { color: rgb(181, 137, 0); }
div.CodeMirror span.CodeMirror-matchingbracket { color: rgb(0, 255, 0); }
div.CodeMirror span.CodeMirror-nonmatchingbracket { color: rgb(255, 34, 34); }
.cm-s-inner .CodeMirror-activeline-background { background: inherit; }
.CodeMirror { position: relative; overflow: hidden; }
.CodeMirror-scroll { height: 100%; outline: 0px; position: relative; box-sizing: content-box; background: inherit; }
.CodeMirror-sizer { position: relative; }
.CodeMirror-gutter-filler, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-vscrollbar { position: absolute; z-index: 6; display: none; outline: 0px; }
.CodeMirror-vscrollbar { right: 0px; top: 0px; overflow: hidden; }
.CodeMirror-hscrollbar { bottom: 0px; left: 0px; overflow: auto hidden; }
.CodeMirror-scrollbar-filler { right: 0px; bottom: 0px; }
.CodeMirror-gutter-filler { left: 0px; bottom: 0px; }
.CodeMirror-gutters { position: absolute; left: 0px; top: 0px; padding-bottom: 10px; z-index: 3; overflow-y: hidden; }
.CodeMirror-gutter { white-space: normal; height: 100%; box-sizing: content-box; padding-bottom: 30px; margin-bottom: -32px; display: inline-block; }
.CodeMirror-gutter-wrapper { position: absolute; z-index: 4; background: 0px 0px !important; border: none !important; }
.CodeMirror-gutter-background { position: absolute; top: 0px; bottom: 0px; z-index: 4; }
.CodeMirror-gutter-elt { position: absolute; cursor: default; z-index: 4; }
.CodeMirror-lines { cursor: text; }
.CodeMirror pre { border-radius: 0px; border-width: 0px; background: 0px 0px; font-family: inherit; font-size: inherit; margin: 0px; white-space: pre; overflow-wrap: normal; color: inherit; z-index: 2; position: relative; overflow: visible; }
.CodeMirror-wrap pre { overflow-wrap: break-word; white-space: pre-wrap; word-break: normal; }
.CodeMirror-code pre { border-right: 30px solid transparent; width: fit-content; }
.CodeMirror-wrap .CodeMirror-code pre { border-right: none; width: auto; }
.CodeMirror-linebackground { position: absolute; inset: 0px; z-index: 0; }
.CodeMirror-linewidget { position: relative; z-index: 2; overflow: auto; }
.CodeMirror-wrap .CodeMirror-scroll { overflow-x: hidden; }
.CodeMirror-measure { position: absolute; width: 100%; height: 0px; overflow: hidden; visibility: hidden; }
.CodeMirror-measure pre { position: static; }
.CodeMirror div.CodeMirror-cursor { position: absolute; visibility: hidden; border-right: none; width: 0px; }
.CodeMirror div.CodeMirror-cursor { visibility: hidden; }
.CodeMirror-focused div.CodeMirror-cursor { visibility: inherit; }
.cm-searching { background: rgba(255, 255, 0, 0.4); }
span.cm-underlined { text-decoration: underline; }
span.cm-strikethrough { text-decoration: line-through; }
.cm-tw-syntaxerror { color: rgb(255, 255, 255); background-color: rgb(153, 0, 0); }
.cm-tw-deleted { text-decoration: line-through; }
.cm-tw-header5 { font-weight: 700; }
.cm-tw-listitem:first-child { padding-left: 10px; }
.cm-tw-box { border-style: solid; border-right-width: 1px; border-bottom-width: 1px; border-left-width: 1px; border-color: inherit; border-top-width: 0px !important; }
.cm-tw-underline { text-decoration: underline; }
@media print {
 .CodeMirror div.CodeMirror-cursor { visibility: hidden; }
}



:root {
 --side-bar-bg-color: #fafafa;
 --control-text-color: #777;
}

@include-when-export url(https://fonts.googleapis.com/css?family=Open+Sans:400italic,700italic,700,400&subset=latin,latin-ext);

/* open-sans-regular - latin-ext\_latin */
 /* open-sans-italic - latin-ext\_latin */
 /* open-sans-700 - latin-ext\_latin */
 /* open-sans-700italic - latin-ext\_latin */
 html {
 font-size: 16px;
 -webkit-font-smoothing: antialiased;
}

body {
 font-family: "Open Sans","Clear Sans", "Helvetica Neue", Helvetica, Arial, 'Segoe UI Emoji', 'SF Pro', sans-serif;
 color: rgb(51, 51, 51);
 line-height: 1.6;
}

#write {
 max-width: 860px;
 margin: 0 auto;
 padding: 30px;
 padding-bottom: 100px;
}

@media only screen and (min-width: 1400px) {
 #write {
 max-width: 1024px;
 }
}

@media only screen and (min-width: 1800px) {
 #write {
 max-width: 1200px;
 }
}

#write > ul:first-child,
#write > ol:first-child{
 margin-top: 30px;
}

a {
 color: #4183C4;
}
h1,
h2,
h3,
h4,
h5,
h6 {
 position: relative;
 margin-top: 1rem;
 margin-bottom: 1rem;
 font-weight: bold;
 line-height: 1.4;
 cursor: text;
}
h1:hover a.anchor,
h2:hover a.anchor,
h3:hover a.anchor,
h4:hover a.anchor,
h5:hover a.anchor,
h6:hover a.anchor {
 text-decoration: none;
}
h1 tt,
h1 code {
 font-size: inherit;
}
h2 tt,
h2 code {
 font-size: inherit;
}
h3 tt,
h3 code {
 font-size: inherit;
}
h4 tt,
h4 code {
 font-size: inherit;
}
h5 tt,
h5 code {
 font-size: inherit;
}
h6 tt,
h6 code {
 font-size: inherit;
}
h1 {
 font-size: 2.25em;
 line-height: 1.2;
 border-bottom: 1px solid #eee;
}
h2 {
 font-size: 1.75em;
 line-height: 1.225;
 border-bottom: 1px solid #eee;
}

/*@media print {
 .typora-export h1,
 .typora-export h2 {
 border-bottom: none;
 padding-bottom: initial;
 }

 .typora-export h1::after,
 .typora-export h2::after {
 content: "";
 display: block;
 height: 100px;
 margin-top: -96px;
 border-top: 1px solid #eee;
 }
}*/

h3 {
 font-size: 1.5em;
 line-height: 1.43;
}
h4 {
 font-size: 1.25em;
}
h5 {
 font-size: 1em;
}
h6 {
 font-size: 1em;
 color: #777;
}
p,
blockquote,
ul,
ol,
dl,
table{
 margin: 0.8em 0;
}
li>ol,
li>ul {
 margin: 0 0;
}
hr {
 height: 2px;
 padding: 0;
 margin: 16px 0;
 background-color: #e7e7e7;
 border: 0 none;
 overflow: hidden;
 box-sizing: content-box;
}

li p.first {
 display: inline-block;
}
ul,
ol {
 padding-left: 30px;
}
ul:first-child,
ol:first-child {
 margin-top: 0;
}
ul:last-child,
ol:last-child {
 margin-bottom: 0;
}
blockquote {
 border-left: 4px solid #dfe2e5;
 padding: 0 15px;
 color: #777777;
}
blockquote blockquote {
 padding-right: 0;
}
table {
 padding: 0;
 word-break: initial;
}
table tr {
 border: 1px solid #dfe2e5;
 margin: 0;
 padding: 0;
}
table tr:nth-child(2n),
thead {
 background-color: #f8f8f8;
}
table th {
 font-weight: bold;
 border: 1px solid #dfe2e5;
 border-bottom: 0;
 margin: 0;
 padding: 6px 13px;
}
table td {
 border: 1px solid #dfe2e5;
 margin: 0;
 padding: 6px 13px;
}
table th:first-child,
table td:first-child {
 margin-top: 0;
}
table th:last-child,
table td:last-child {
 margin-bottom: 0;
}

.CodeMirror-lines {
 padding-left: 4px;
}

.code-tooltip {
 box-shadow: 0 1px 1px 0 rgba(0,28,36,.3);
 border-top: 1px solid #eef2f2;
}

.md-fences,
code,
tt {
 border: 1px solid #e7eaed;
 background-color: #f8f8f8;
 border-radius: 3px;
 padding: 0;
 padding: 2px 4px 0px 4px;
 font-size: 0.9em;
}

code {
 background-color: #f3f4f4;
 padding: 0 2px 0 2px;
}

.md-fences {
 margin-bottom: 15px;
 margin-top: 15px;
 padding-top: 8px;
 padding-bottom: 6px;
}


.md-task-list-item > input {
 margin-left: -1.3em;
}

@media print {
 html {
 font-size: 13px;
 }
 pre {
 page-break-inside: avoid;
 word-wrap: break-word;
 }
}

.md-fences {
 background-color: #f8f8f8;
}
#write pre.md-meta-block {
 padding: 1rem;
 font-size: 85%;
 line-height: 1.45;
 background-color: #f7f7f7;
 border: 0;
 border-radius: 3px;
 color: #777777;
 margin-top: 0 !important;
}

.mathjax-block>.code-tooltip {
 bottom: .375rem;
}

.md-mathjax-midline {
 background: #fafafa;
}

#write>h3.md-focus:before{
 left: -1.5625rem;
 top: .375rem;
}
#write>h4.md-focus:before{
 left: -1.5625rem;
 top: .285714286rem;
}
#write>h5.md-focus:before{
 left: -1.5625rem;
 top: .285714286rem;
}
#write>h6.md-focus:before{
 left: -1.5625rem;
 top: .285714286rem;
}
.md-image>.md-meta {
 /*border: 1px solid #ddd;*/
 border-radius: 3px;
 padding: 2px 0px 0px 4px;
 font-size: 0.9em;
 color: inherit;
}

.md-tag {
 color: #a7a7a7;
 opacity: 1;
}

.md-toc { 
 margin-top:20px;
 padding-bottom:20px;
}

.sidebar-tabs {
 border-bottom: none;
}

#typora-quick-open {
 border: 1px solid #ddd;
 background-color: #f8f8f8;
}

#typora-quick-open-item {
 background-color: #FAFAFA;
 border-color: #FEFEFE #e5e5e5 #e5e5e5 #eee;
 border-style: solid;
 border-width: 1px;
}

/** focus mode */
.on-focus-mode blockquote {
 border-left-color: rgba(85, 85, 85, 0.12);
}

header, .context-menu, .megamenu-content, footer{
 font-family: "Segoe UI", "Arial", sans-serif;
}

.file-node-content:hover .file-node-icon,
.file-node-content:hover .file-node-open-state{
 visibility: visible;
}

.mac-seamless-mode #typora-sidebar {
 background-color: #fafafa;
 background-color: var(--side-bar-bg-color);
}

.mac-os #write{
 caret-color: AccentColor;
}

.md-lang {
 color: #b4654d;
}

/*.html-for-mac {
 --item-hover-bg-color: #E6F0FE;
}*/

#md-notification .btn {
 border: 0;
}

.dropdown-menu .divider {
 border-color: #e5e5e5;
 opacity: 0.4;
}

.ty-preferences .window-content {
 background-color: #fafafa;
}

.ty-preferences .nav-group-item.active {
 color: white;
 background: #999;
}

.menu-item-container a.menu-style-btn {
 background-color: #f5f8fa;
 background-image: linear-gradient( 180deg , hsla(0, 0%, 100%, 0.8), hsla(0, 0%, 100%, 0)); 
}

ol, ul {padding-left: 40px}
README


# Appian Platform (CS) Helm Chart

A Helm chart for deploying the Appian platform on Kubernetes. This Helm chart is supplied by Appian Customer Success via the Appian App Market.

This chart deploys a custom resource of type `appian` that is managed by the [Appian Operator](https://docs.appian.com/suite/help/latest/k8s/what-is-appian-operator.html).

## Introduction

This chart facilitates the deployment of Appian sites through templated support for common options while baking-in best practice configurations.

## Prerequisites

* [Deployment prerequisites](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#prerequisites)


* [Appian operator](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#1-install-the-appian-operator)



The Config Generator tool from [Appian Kubernetes Utilities](https://community.appian.com/b/appmarket/posts/appian-kubernetes-utilities), available from the Appian App Market, can help you prepare these prerequisites.

## Usage

### Review templated custom resource specification

Want to see what custom resource specification your values file would produce? You can preview your Appian custom resource manifest by preparing your values file and running the following:


```

```
helm template -f values.yaml appian-platform-cs-$CHART\_VERSION.tgz > appian-site.yaml
```

```

> Note: You need to substitute the placeholder `CHART_VERSION` with the version of chart you are using. A YAML file that specifies the values for the parameters must be provided (e.g. `values.yaml`).
> 
> 

Or if you have already deployed the chart to your Helm repository:


```

```
xxxxxxxxxx
```

```
helm template -f values.yaml oci://$REGISTRY\_NAME/$REPOSITORY\_NAME/appian-platform-cs --version $CHART\_VERSION > appian-site.yaml
```

```

> Note: You need to substitute the placeholders `REGISTRY_NAME` and `REPOSITORY_NAME` with a reference to your Helm chart registry and repository. A YAML file that specifies the values for the parameters must be provided (e.g. `values.yaml`).
> 
> 

### Deploying or restarting the Appian site (Installing the chart)

To install the chart with the release name `$SITE_NAME`:


```

```
xxxxxxxxxx
```

```
helm install $SITE\_NAME --namespace appian -f values.yaml --wait oci://$REGISTRY\_NAME/$REPOSITORY\_NAME/appian-platform-cs --version $CHART\_VERSION
```

```

> Note: You need to substitute the placeholders `REGISTRY_NAME` and `REPOSITORY_NAME` with a reference to your Helm chart registry and repository. A YAML file that specifies the values for the parameters must be provided (e.g. `values.yaml`) while installing the chart.
> 
> 

### Stopping the Appian site (Deleting the chart)

To stop the Appian site with the release name `$SITE_NAME`:


```

```
xxxxxxxxxx
```

```
helm uninstall $SITE\_NAME --namespace appian
```

```
This will not delete the Persistent Volume Claims nor the associated RDBMS and as such leaves the site's data in place ready for when the site is next started again.

### Upgrading or hotfixing the Appian site

To upgrade the Appian site to a new major version, or to hoftix the site with newer container images for the same major version:

1. [Stop the Appian site](\#stopping-the-appian-site-deleting-the-chart) (Ensure the site stops cleanly with all checkpoints completed).


2. Update the value of `url` in your values file to reference your new target version


3. [Start the Appian site](\#deploying-or-restarting-the-appian-site-installing-the-chart)



Ensure you check the [operator release notes](https://docs.appian.com/suite/help/latest/k8s/release-notes.html) and [platform release notes](https://docs.appian.com/suite/help/latest/Appian_Release_Notes.html) before upgrading an Appian site and provision the relevant container images and Operator Helm chart in your container registry.

### Upgrading this Helm chart

To upgrade to a later version of this Helm chart, ensure you check the [Release Notes](#release-notes) for any changes. Before upgrading, use the `helm template` command to compare the output generated by the new version of the chart with your existing configuration.

## Example values files

This section provides some sample values files illustrating certain configuration options.


> Note: These few examples are not exhaustive and do not represent all possible configurations.
> 
> 

### Example 1 - Non-HA, MariaDB, AWS Load Balancer

Spec overview:

* Non-HA


* class "small"


* MariaDB primary data source


* AWS Load Balancer ingress, with SSL configured via an AWS certificate


* Container registry authenticated via images.pullSecrets




```

```
xxxxxxxxxx
```

```
siteName: company-proj-dev
```

```
version: "24.3.100.0"
```

```
url: https://proj-dev.company.com
```

```
staticUrl: https://proj-dev.company-static.com
```

```
dynamicUrl: https://proj-dev.company-dynamic.com
```

```
class: small
```

```
# Non-HA
```

```
highAvailability: false
```

```
passwordsPropertiesSecretName: "passwords-properties"
```

```
license:
```

```
 k3SecretName: "k3lic"
```

```
 k4SecretName: "k4lic"
```

```
 appianConfigMapName: "appian-lic"
```

```
storage:
```

```
 rwoStorageClassName: "my-ebs-sc"
```

```
 sharedLogsPvc: "appian-shared-logs-pvc"
```

```
images:
```

```
 pullSecrets:
```

```
   - regcred
```

```
 appian:
```

```
   repository: "my.container.registry.com/appian"
```

```
 minimal:
```

```
   repository: alpine
```

```
   tag: "3.18.0"
```

```
smtp:
```

```
 senderAddress: "my\_from\_address@my\_domain.com"
```

```
 senderDomain: "my\_domain.com"
```

```
 host: "my.smtp.server.smtp.com"
```

```
 auth: true
```

```
 user: "my\_user\_name"
```

```
 protocol: "smtp"
```

```
 starttlsEnabled: false
```

```
 starttlsRequired: false
```

```
dataSources:
```

```
  # MariaDB primary data source
```

```
 primary:
```

```
   name: jdbc/AppianPrimary
```

```
   dbType: mariadb
```

```
   dbServerAndPort: my.database.server.com:3306
```

```
   schemaName: "appian\_primary"
```

```
   usernameSecretKeyRef:
```

```
     name: "appian-primary-ds"
```

```
     key: "username"
```

```
   passwordSecretKeyRef:
```

```
     name: "appian-primary-ds"
```

```
     key: "password"
```

```
ingressTemplate:
```

```
  # AWS Load Balancer ingress
```

```
 name: alb
```

```
  # SSL configured via an AWS certificate
```

```
 certificateReference: "my-cert-arn"
```

```
### Example 2 - HA, MySQL, NGINX

Spec overview:

* HA


* class "medium"


* MySQL primary and one business data source


* NGINX ingress, with SSL configured via TLS field


* Node selector targeting dedicated Appian node group


* Kafka storage size (set by class template) overridden


* Data Service class upscaled to "large"


* Self-managed monitoring metrics API enabled




```

```
xxxxxxxxxx
```

```
siteName: company-proj-dev
```

```
version: "24.3.100.0"
```

```
url: https://proj-dev.company.com
```

```
staticUrl: https://proj-dev.company-static.com
```

```
dynamicUrl: https://proj-dev.company-dynamic.com
```

```
class: medium
```

```
# HA
```

```
highAvailability: true
```

```
passwordsPropertiesSecretName: "passwords-properties"
```

```
# Self-Managed Monitoring Metrics API
```

```
metricsAuthToken: "bW9uaXRvcmluZw=="
```

```
# Node selector targeting dedicated Appian node group
```

```
nodeSelector:
```

```
 my-node-group-label-key: my-node-group-label-value
```

```
license:
```

```
 k3SecretName: "k3lic"
```

```
 k4SecretName: "k4lic"
```

```
 appianConfigMapName: "appian-lic"
```

```
storage:
```

```
 rwoStorageClassName: "my-rwo-sc"
```

```
 sharedLogsPvc: "appian-shared-logs-pvc"
```

```
 haSharedDataPvc: "appian-shared-data-pvc"
```

```
images:
```

```
 appian:
```

```
   repository: "my.container.registry.com/appian"
```

```
 minimal:
```

```
   repository: alpine
```

```
   tag: "3.18.0"
```

```
smtp:
```

```
 senderAddress: "my\_from\_address@my\_domain.com"
```

```
 senderDomain: "my\_domain.com"
```

```
 host: "my.smtp.server.smtp.com"
```

```
 auth: true
```

```
 user: "my\_user\_name"
```

```
 protocol: "smtp"
```

```
 starttlsEnabled: false
```

```
 starttlsRequired: false
```

```
dataSources:
```

```
  # MySQL primary
```

```
 primary:
```

```
   name: jdbc/AppianPrimary
```

```
   dbType: mysql
```

```
   dbServerAndPort: my.database.server.com:3306
```

```
   schemaName: "appian\_primary"
```

```
   usernameSecretKeyRef:
```

```
     name: "appian-primary-ds"
```

```
     key: "username"
```

```
   passwordSecretKeyRef:
```

```
     name: "password-secret-appian-primary-ds"
```

```
     key: "password"
```

```
  # one business data source
```

```
 business:
```

```
   - name: jdbc/Appian
```

```
     dbType: mysql
```

```
     dbServerAndPort: my.database.server.com:3306
```

```
     schemaName: "appian"
```

```
     usernameSecretKeyRef:
```

```
 name: "appian-business-ds"
```

```
  key: "username"
```

```
     passwordSecretKeyRef:
```

```
       name: "appian-business-ds"
```

```
       key: "password"
```

```
ingressTemplate:
```

```
  # NGINX ingress
```

```
 name: nginx
```

```
  # SSL configured via TLS field
```

```
 tls:
```

```
   - hosts:
```

```
       - proj-dev.company.com
```

```
       - proj-dev.company-static.com
```

```
       - proj-dev.company-dynamic.com
```

```
     secretName: appian-ingress-tls-secret
```

```
# Kafka storage size (set by class template) overridden
```

```
kafka:
```

```
 storageSize: "60Gi"
```

```
dataServer:
```

```
 class: "large"
```

```
## Limitations

A number of fields in the Custom Resource are immutable. These must not be modified for a running site, so any Helm upgrades to the chart must avoid changing these values. To be able to change these immutable fields, the Appian site needs to be stopped (by [deleting the chart](#stopping-the-appian-site-deleting-the-chart)) and restarted (by [installing the chart](#deploying-or-restarting-the-appian-site-installing-the-chart) with updated values).

As `version` is one of these immutable fields, Appian hotfixes and major version upgrades cannot be applied using `helm upgrade` and require the site to be stopped and restarted as above.

## T-Shirt Sizing

This Helm chart uses a `class` parameter to apply default values for a range of size- and scaling-related parameters, which can then be fine-tuned using [component-level overrides](#per-component-overrides-and-additional-parameters). An appropriate t-shirt size should be chosen as a starting configuration. Performance testing should be used to determine whether to change class or, alternatively, to override certain parameters set by class templates.


> For example, a site with higher process throughput may require larger Kafka storage and additional resources for just the execution engines - which can be achieved by overriding just those parameters, while all other relevant parameters are left as set by the chosen class.
> 
> 

The table below provides very rough guidelines for each class, including the expected resources required to run each size.



| Class | Purpose | Resources Required (Non-HA) | Resources Required (HA) |
| --- | --- | --- | --- |
| `x-small` | Development or Single Application | 8 CPU / 64 GB RAM115 GB RWO100 GB RWX (Logs) | CPU / RAM x3186 GB RWO200 GB RWX (Logs) / 100 GB RWX (Data) |
| `small` | Development or Single Application | 16 CPU / 128 GB RAM115 GB RWO100 GB RWX (Logs) | CPU / RAM x3186 GB RWO200 GB RWX (Logs) / 100 GB RWX (Data) |
| `medium` | Departmental adoption | 24 CPU / 192 GB RAM150 GB RWO150 GB RWX (Logs) | CPU / RAM x3291 GB RWO300 GB RWX (Logs) / 200 GB RWX (Data) |
| `large` | Enterprise adoption | 48 CPU / 384 GB RAM210 GB RWO200 GB (Logs) | CPU / RAM x3342 GB RWO400 GB RWX (Logs) / 300 GB RWX (Data) |
| `x-large` | Enterprise adoption | 64 CPU / 512 GB RAM210 GB RWO200 GB (Logs) | CPU / RAM x3342 GB RWO400 GB RWX (Logs) / 300 GB RWX (Data) |

*Assumes 3 Exec/Analytics shards without RPA or AI. Initial sizing only. Performance testing / observation and resource request / compute right-sizing is required.*

## Parameters

### General parameters



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `siteName` | string | `""` | Appian site name. Must match the wildcard pattern of the licenses provided. See [request licenses](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#request-licenses). **This field is immutable.** | true | `metadata.name` |
| `version` | string | `""` | The Low-Code Platform (LCP) version. This field will be required in a future release. **This field is immutable.** | true | `spec.version` |
| `url` | string | `""` | The scheme, host, and, optionally, port used to access Appian (e.g. `https://appian.example.com`, `http://appian.example.com:32767`, etc). *For sites with a single Webapp replica, updating this field requires restarting Webapp's pod.* | true | `spec.url` |
| `staticUrl` | string | `""` | The scheme, host, and, optionally, port for Appian's static content URL (e.g. `https://appian.example-static.com`, `http://appian.example-static.com:32767`, etc). The scheme must be the same as that defined in `spec.url`. Must use a different domain from `spec.url` and `dynamicUrl`. *For sites with a single Webapp replica, updating this field requires restarting Webapp's pod.* See [Configure Your Static and Dynamic Content URLs](https://docs.appian.com/suite/help/latest/Post-Install_Configurations.html#configure-your-static-and-dynamic-content-urls) for more info. | false | `spec.webapp.staticUrl` |
| `dynamicUrl` | string | `""` | The scheme, host, and, optionally, port for Appian's dynamic content URL (e.g. `https://appian.example-dynamic.com`, `http://appian.example-dynamic.com:32767`, etc). The scheme must be the same as that defined in `spec.url`. Must use a different domain from `spec.url` and `staticUrl`. *For sites with a single Webapp replica, updating this field requires restarting Webapp's pod.* See [Configure Your Static and Dynamic Content URLs](https://docs.appian.com/suite/help/latest/Post-Install_Configurations.html#configure-your-static-and-dynamic-content-urls) for more info. | false | `spec.webapp.dynamicUrl` |
| `class` | enum | `""` | One of `"x-small", "small"`, `"medium"`, `"large", "x-large"`.Changing `class` after an initial deployment will not automatically affect all sizings driven by it (e.g. disk volume sizes will not change). **This field is immutable.**See [class](#t-shirt-sizing). | true | Multiple fields across all components. |
| `enableCpuLimits` | bool | `false` | Determines whether to apply CPU limits to pods. By default, no CPU limits are set. Setting this field to `true` will apply the class's defaults for each pod type, unless overridden by `defaultCpuLimits` or `[component].resources.limits.cpu`. When CPU limits are enabled (when `enableCpuLimits: true`), the order of precedence for each component is 1. Component-level CPU limits override, 2. Global `defaultCpuLimits`, 3. Class CPU limits. | false | `spec.[component]``.resources.limits.cpu` |
| `defaultCpuLimits` | int or string | `nil` | Default CPU limits to set if not disabling CPU limits and not using the built-in class's CPU limits. Only applied if `enableCpuLimits: true`. Can be overridden for a specific component by setting `[component].resources.limits.cpu`. | false | `spec.[component]``.resources.limits.cpu` |
| `enableResourceRequests` | bool | `true` | When set to `false` this sets CPU and Memory resource requests to `0` for each component. Overrides all other configurations for these fields.Only used when running on small, dedicated worker nodes. Must be used in conjunction with `nodeSelector` (see [T-Shirt Sizing](#t-shirt-sizing)). | false | `spec.[component]``.resources.requests.cpu``spec.[component]``.resources.requests.memory` |
| `highAvailability` | bool | `false` | Determines whether the environment will be deployed in a High Availability (HA) configuration.Changing `highAvailability` after an initial deployment will not automatically change the topology of the site. **This field is immutable.** | false | Multiple fields across all components. |
| `passwordsPropertiesSecretName` | string | `""` | Name of an existing secret containing Appian's `passwords.properties` file. If using an authenticated SMTP server, the file should contain `conf.password.SMTP=$YOUR_SMTP_PASSWORD_HERE` *For sites with a single Webapp replica, updating this field requires restarting Webapp's pod.* | false**Required when** `smtp.auth` **is** `true`**.** | `spec.webapp``.passwordsPropertiesSecretName` |
| `metricsAuthToken` | string | `""` | Base64 encoded password for authenticating to the Appian self-managed monitoring metrics API. Setting this field automatically sets two custom properties: `metricsauthtoken` (to this value) and `appian.feature.selfManagedMonitoring` (to `true`). See [Self-Managed Monitoring](https://gitlab.com/appian-oss/self-managed-monitoring) for details of this solution. | false | `spec.customProperties` |
| `additionalCustomProperties` | object | `{}` | Additional custom properties in addition to [those set by the chart automatically](#managed-custom-properties). See [Custom Properties](https://docs.appian.com/suite/help/latest/Custom_Configurations.html#custom-properties) for more info. Note: Do not set any custom properties here that are set by this chart by default. Doing so will result in duplicate entries for that property under `spec.customProperties`. | false | `spec.customProperties` |
| `nodeSelector` | object | `{}` | A selector which must be true for the components' pod(s) to fit on a node. See [nodeSelector](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector) for more info. Can be overridden for a specific component by setting `[component].nodeSelector`. | false | `spec.[component]``.nodeSelector` |
| `securityContext` | object | `{}` | Container-level security context applied to all components. Passthrough to [`corev1.SecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#securitycontext-v1-core). See [securityContext](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1securitycontext) for more info. Can be overridden for a specific component by setting `[component].securityContext`. | false | `spec.[component]``.securityContext` |
| `podSecurityContext` | object | `{}` | Pod-level security context applied to all components. Passthrough to [`corev1.PodSecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#podsecuritycontext-v1-core). Requires Appian Operator v0.200.0+. Can be overridden for a specific component by setting `[component].podSecurityContext`. | false | `spec.[component]``.podSecurityContext` |
| `rbac` | object | `{}` | Configuration for creating RBAC resources. | false | `spec.rbac` |
| `networkPolicies` | object | `{}` | Configuration for creating network policy resources. | false | `spec.networkPolicies` |
| `additionalLabels` | object | `{}` | Additional labels for created objects - including pods. *For stateful components with a single replica, updating this field requires restarting the component's pod.* | false | `spec.additionalLabels` |
| `cascadeVersionToComponentTags` | bool | `false` | Whether to set `[component].image.tag` to the value of `version`. Only required if using the Appian Migration Tool, which enforces that `{component}.image.tag` is present. | false | `spec.[component].image.tag` |

### License parameters



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `license.k3SecretName` | string | `"k3lic"` | Name of the existing secret containing the `k3.lic` file. Defaults to `k3lic`. *For sites with a single replica of service-manager, updating this field requires restarting all service-manager pods.* | true | `spec.k3LicSecretName` |
| `license.k4SecretName` | string | `"k4lic"` | Name of the existing secret containing the `k4.lic` file. Defaults to `k4lic`. *For sites with a single Data Service replica, updating this field requires restarting Data Service's pod.* | true | `spec.k4LicSecretName` |
| `appianConfigMapName` | string | `"appian-lic"` | Name of the existing config map containing the `appian.lic` file. | true | `spec.appianLicConfigMapName` |

### Storage parameters



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `storage.rwoStorageClassName` | string | `""` | Name of an existing Storage Class for provisioning ReadWriteOnce (RWO) storage for the Appian stateful pods.Changing `rwoStorageClassName` after an initial deployment will not automatically change the storage class of the provisioned RWO volumes. | true | `spec.[component]``.volumeClaimTemplateSpec.storageClassName` |
| `storage.sharedLogsPvc` | string | `""` | Name of an existing ReadWriteMany (RWX) persistent volume claim to be used for Appian shared logs (aka [Health Check](https://docs.appian.com/suite/help/latest/health-check.html)) storage. Must differ from `haSharedDataPvc`. **This field is immutable.** See [Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) for more info. | false[Not required but strongly recommended for all environments] | `spec.webapp.healthCheckExistingClaim` |
| `storage.haSharedDataPvc` | string | `""` | Name of an existing ReadWriteMany (RWX) persistent volume claim to be used for shared data. Must differ from `sharedLogsPvc`. Required for HA environments. For non-HA environments that may be converted to HA in future, setting this field from the start (in addition to `storage.sharedLogsPvc`) makes it easier to convert the environment. This field cannot be set *after* initial creation of an environment without manual data copy operations! **This field is immutable.** See [Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) for more info. | false**Required when** `highAvailability` **is** `true`**.** | `spec.webapp.haExistingClaim`, `spec.serviceManager.haExistingClaim` |

### Images parameters



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `images.pullSecrets` | list | `[]` | Names of existing image pull secrets. See [Pull an Image from a Private Registry](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/) for more info. | false | `spec.imagePullSecrets` |
| `images.appian.repository` | string | `""` | The URL to which `/[component]` can be added to reference each of the Appian component container images (e.g. `my.container.registry.com/appian`) | true | `spec.[component]``.image.repository` |
| `images.minimal.repository` | string | `busybox` | The path to the minimal container image to use where required. This should be the full image path (e.g. `my.container.registry.com/alpine` or `busybox`). Required if not disabling the built-in Search Server init container (via `searchServer.setVmMaxMapCount: false`). | false | Any init containers configured by the chart (e.g. Search Server vm max map count init container) |
| `images.minimal.tag` | string | `""` | The tag to use for the minimal image. Required if not disabling the built-in Search Server init container (via `searchServer.setVmMaxMapCount: false`). | false | Any init containers configured by the chart (e.g. Search Server vm max map count init container) |

### SMTP parameters



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `smtp.senderAddress` | string | `""` | The address that will appear as the sender (the "From" address) of notification and password reset emails from the system | false | `spec.customProperties` |
| `smtp.senderDomain` | string | `""` | The domain (portion after the "@") for the "from" email address for addresses created via expressions functions; also applies to the domain for alert emails when the custom property `conf.mailhandler.ntf_sndr_addr` is not set | false | `spec.customProperties` |
| `smtp.host` | string | `""` | The host is the FQDN, hostname, or IP address of the SMTP server for sending email from the system. Muliple SMTP servers can be specified using a comma-separated list. They will be tried in the order specified. If a port other than 25 is required, append it to the hostname (e.g. `mailhost3:9025`). If this is not set, no email will be sent from the system. The Helm chart will not add SMTP-related custom properties if `smtp.host` is not set. | false | `spec.customProperties` |
| `smtp.auth` | bool | `false` | Set to `true` if user/password authentication to the SMTP server is used. Leave the default (`false`) to indicate that the SMTP server does not require authentication. If multiple SMTP servers are defined above, the same auth settings will apply to all servers | false | `spec.customProperties` |
| `smtp.user` | string | `""` | The username used to connect to the SMTP server | false | `spec.customProperties` |
| `smtp.protocol` | string | `"smtp"` | The protocol should be set to either `smtp` or `smtps`. | false | `spec.customProperties` |
| `smtp.starttlsEnabled` | string | `""` | You can enable or require STARTTLS with the `smtp` protocol. Setting `smtp.starttlsEnabled` to `true` will cause outgoing mail to use STARTTLS if supported by the remote server, but will fall back to plain smtp otherwise | false | `spec.customProperties` |
| `smtp.starttlsRequired` | string | `""` | Setting `smtp.starttlsRequired` to `true` will cause mail to fail if the remote server does not support STARTTLS | false | `spec.customProperties` |

### Data Sources parameters

The `datasources` field allows primary and business data sources to be configured with ease via built-in templates for each [supported RDBMS](https://docs.appian.com/suite/help/latest/System_Requirements.html#databases).



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `dataSources.primary` | [Data Source Template](#primary-data-source-parameters) object | `{}` | The data source for the Appian primary database. See [Data Source Template parameters](#data-source-template-parameters). Ignored if `webapp.dataSources` is provided! | true | `spec.webapp``.dataSources.primary` |
| `dataSources.business` | [Data Source Template](#primary-data-source-parameters) list | `[]` | Optional business data sources. List of [Data Source Template](#data-source-template-parameters). Ignored if `webapp.dataSources` is provided! | false | `spec.webapp``.dataSources.primary` |

#### Data Source Template parameters

The following parameters are available for `dataSources.primary` and for each item in the list `dataSources.business`. The chart's Data Source Templates make it simpler to apply the correct configurations for each data source with fewer, simpler parameters to be configured.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `name` | string | `""` | The JNDI name for the data source (e.g. `jdbc/AppianPrimary`). | true | `spec.webapp.dataSources``.[primary/business.[]].name` |
| `dbType` | string | `""` | One of `"mariadb"`, `"mysql"`, `"mysql-aurora"`, `"oracle"`, `"mssql"`, `"postgresql"`, `"postgresql-aurora"`, `"db2"`. | true | `spec.webapp.dataSources``.[primary/business.[]].driverClassName``spec.webapp.dataSources``.[primary/business.[]].url` |
| `dbServerAndPort` | string | `""` | The server and port for the target database (e.g. `my.database.com:3306`). | true | `spec.webapp.dataSources``.[primary/business.[]].url` or `spec.webapp.dataSources``.[primary/business.[]].url` |
| `schemaName` | string | `""` | The schema name for the target database. For Oracle this is the service name. For MS SQL this is the database name. E.g. `appian_primary` | true | `spec.webapp.dataSources``.[primary/business.[]].url` or `spec.webapp.dataSources``.[primary/business.[]].url` |
| `urlParameters` | string | `""` | A string of appropriately separated connection string query parameters.For MySQL and MariaDB do not include `useOldAliasMetadataBehavior` (this is prepended by the chart).For MSSQL do not include `databaseName` or `socketTimeout` (these are prepended by the chart).Do not include leading `?`, `;` or `&` at the start. | false | `spec.webapp.dataSources``.[primary/business.[]].url` or `spec.webapp.dataSources``.[primary/business.[]].url` |
| `usernameSecretKeyRef.name` | string | `""` | Name of an existing secret holding the username used to connect to the data source (e.g. `appian-primary-ds`). | true | `spec.webapp.dataSources``.[primary/business.[]].usernameSecretKeyRef.name` |
| `usernameSecretKeyRef.key` | string | `""` | Key within the existing secret `dataSources.primary.usernameSecretKeyRef.name` holding the username used to connect to the data source (e.g. `username`). | true | `spec.webapp.dataSources``.[primary/business.[]].usernameSecretKeyRef.key` |
| `passwordSecretKeyRef.name` | string | `""` | Name of an existing secret holding the password used to connect to the data source (e.g. `appian-primary-ds`). | true | `spec.webapp.dataSources``.[primary/business.[]].passwordSecretKeyRef.name` |
| `passwordSecretKeyRef.key` | string | `""` | Key within the existing secret `dataSources.primary.passwordSecretKeyRef.name` holding the password used to connect to the data source (e.g. `password`). | true | `spec.webapp.dataSources``.[primary/business.[]].passwordSecretKeyRef.key` |
| `attributes` | object | `{}` | Optionally replaces the default set of attributes in `spec.webapp.dataSources.[primary/business.[]].attributes`. If not provided, the chart applies the default set of attributes as defined in [Configuring Relational Databases](https://docs.appian.com/suite/help/latest/Configuring_Relational_Databases.html#provide-data-source-connection-information). | false | `spec.webapp.dataSources``.[primary/business.[]].attributes` |

### Ingress Template parameters

The `ingressTemplate` field allows an ingress to be configured with ease via built-in templates for 4 popular ingress controllers: [NGINX Ingress Controller](https://docs.nginx.com/nginx-ingress-controller/), [AWS Load Balancer Controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller), [Azure Application Gateway Ingress Controller (AGIC)](https://learn.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview) and [OpenShift Default ingress controller](https://github.com/openshift/cluster-ingress-operator). These templates apply standard annotations required for each ingress class.

If you are using another ingress controller, configure this using [Ingress](#ingress) instead.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `ingressTemplate.name` | string | `""` | One of `"nginx"`, `"alb"`, `"agic"`, `"openshift-default"`.The ingress template to apply. | true | `spec.ingress.ingressClassName` |
| `ingressTemplate``.certificateReference` | string | `""` | For `alb`, this is the `certificate-arn`.For `agic` this is `appgw-ssl-certificate` | false | `spec.ingress.annotations` |
| `ingressTemplate``.additionalAnnotations` | object | `{}` | Annotations to configure in addition to those deployed by the chosen ingress template. | false | `spec.ingress.annotations` |
| `ingressTemplate``.tls` | list | `[]` | Configuration for TLS. Not necessary if using `ingressTemplate.certificateReference` for `alb` or `agic`. See [TLS](https://kubernetes.io/docs/concepts/services-networking/ingress/#tls) for more info. | false | `spec.ingress.tls` |
| `ingressTemplate``.hostname` | string | `""` | The hostname used to create the ingress. Useful if you'd like ingress to use an internal hostname different from that used to access Appian. Defaults to the hostname defined in `url`. | false | `spec.ingress.hostname` |
| `ingressTemplate``.staticHostname` | string | `""` | The hostname for Appian's static content URL used to create the ingress. Useful if you'd like ingress to use an internal hostname different from that used to access Appian. Defaults to the hostname defined in `staticUrl`. | false | `spec.ingress.staticHostname` |
| `ingressTemplate``.dynamicHostname` | string | `""` | The hostname for Appian's dynamic content URL used to create the ingress. Useful if you'd like ingress to use an internal hostname different from that used to access Appian. Defaults to the hostname defined in `dynamicUrl`. | false | `spec.ingress.dynamicHostname` |
| `ingressTemplate``.healthcheck.intervalSeconds` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.healthcheck.path` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.healthcheck.port` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.healthcheck.protocol` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.healthcheck.timeoutSeconds` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.healthcheck.healthyThresholdCount` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.healthcheck.unhealthyThresholdCount` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.listenPorts` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.loadBalancerName` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.scheme` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.usePrivateIp` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.trustedRootCertificate` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.successCodes` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.targetType` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |
| `ingressTemplate``.requestTimeout` | string | `""` | Override ingress template value if chosen template applies this value. | false | `spec.ingress.annotations` |

### Replication parameters

The `replication` parameters enable a site to be configured for Kafka real-time transaction replication via MirrorMaker for Kafka mirroring. The site can be configured either as a replication source or destination using these parameters.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `replication.mirrorMaker.mode` | string | `""` | One of `source`, `destination`.Setting `replication.mirrorMaker.mode` to `source` configures this site's Kafka component to expose listeners for a destination site to replicate transactions.Setting `replication.mirrorMaker.mode` to `destination` configures this site's MirrorMaker component to deploy the site in replication mode. | false | `spec.kafka` (when `replication.mirrorMaker.mode` is `source`)`spec.mirrorMaker` (when `replication.mirrorMaker.mode` is `destination`) |
| `replication.mirrorMaker.listeners` | list | `[]` | List of externally addressable Kafka hosts in the source site, used by MirrorMaker in the destination site. The order of the listeners must match the order of Kafka's pods. | false**Required when** `replication.mirrorMaker.mode` **is set.** | `spec.kafka.mirrorMakerListeners` (when `replication.mirrorMaker.mode` is `source`)`spec.mirrorMaker.sourceBrokers` (when `replication.mirrorMaker.mode` is `destination`) |

### Per-Component overrides and additional parameters

Overrides for fields set automatically based on general parameters (e.g. via `class`) and additional optional parameters can be specified at component-level.

#### Zookeeper



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `zookeeper.minHeap` | string | `""` | Override the environment variable `ZK_HEAP_MIN` set by `class`. | false | `spec.zookeeper.env` |
| `zookeeper.maxHeap` | string | `""` | Override the environment variable `ZK_HEAP_MAX` set by `class`. | false | `spec.zookeeper.env` |
| `zookeeper.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.zookeeper``.volumeClaimTemplateSpec.resources``.requests.storage` |
| `zookeeper.resources.requests.cpu` | int or string | `""` | Override the component's CPU requests set by `class`. | false | `spec.zookeeper``.resources.requests.cpu` |
| `zookeeper.resources.limits.cpu` | int or string | `""` | Override the component's CPU limits set by `class`. | false | `spec.zookeeper``.resources.limits.cpu` |
| `zookeeper.resources.requests.memory` | int or string | `""` | Override the component's memory requests set by `class`. | false | `spec.zookeeper``.resources.requests.memory` |
| `zookeeper.resources.limits.memory` | int or string | `""` | Override the component's memory limits set by `class`. | false | `spec.zookeeper``.resources.limits.memory` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Kafka



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `kafka.minHeap` | string | `""` | Override the environment variable `KAFKA_HEAP_MIN` set by `class`. | false | `spec.kafka.env` |
| `kafka.maxHeap` | string | `""` | Override the environment variable `KAFKA_HEAP_MAX` set by `class`. | false | `spec.kafka.env` |
| `kafka.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.kafka``.volumeClaimTemplateSpec.resources``.requests.storage` |
| `kafka.resources.requests.cpu` | int or string | `""` | Override the component's CPU requests set by `class`. | false | `spec.kafka``.resources.requests.cpu` |
| `kafka.resources.limits.cpu` | int or string | `""` | Override the component's CPU limits set by `class`. | false | `spec.kafka``.resources.limits.cpu` |
| `kafka.resources.requests.memory` | int or string | `""` | Override the component's memory requests set by `class`. | false | `spec.kafka``.resources.requests.memory` |
| `kafka.resources.limits.memory` | int or string | `""` | Override the component's memory limits set by `class`. | false | `spec.kafka``.resources.limits.memory` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Search Server



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `searchServer.heap` | string | `""` | Override the environment variable `SS_HEAP` set by `class`. | false | `spec.searchServer.env` |
| `searchServer.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.searchServer``.volumeClaimTemplateSpec.resources``.requests.storage` |
| `searchServer.resources.requests.cpu` | int or string | `""` | Override the component's CPU requests set by `class`. | false | `spec.searchServer``.resources.requests.cpu` |
| `searchServer.resources.limits.cpu` | int or string | `""` | Override the component's CPU limits set by `class`. | false | `spec.searchServer``.resources.limits.cpu` |
| `searchServer.resources.requests.memory` | int or string | `""` | Override the component's memory requests set by `class`. | false | `spec.searchServer``.resources.requests.memory` |
| `searchServer.resources.limits.memory` | int or string | `""` | Override the component's memory limits set by `class`. | false | `spec.searchServer``.resources.limits.memory` |
| `searchServer.setVmMaxMapCount` | boolean | `true` | Deploys a privileged init container to set the worker node kernel's vm.max\_map\_count value to the [required setting](https://docs.appian.com/suite/help/latest/Search_Server.html#search-server-kernel-setting). | false | `spec.searchServer.initContainers` |
| `additionalInitContainers` | list | `[]` | A list of initialization containers belonging to the component to deploy in addition to the default init container configured by the chart for the [Search Server kernel setting](https://docs.appian.com/suite/help/latest/Search_Server.html#search-server-kernel-setting). *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Init Containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) for more info. | false | `spec.[component].initContainers` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Data Service

Note that the Data Service object is called `dataServer` in the Appian CRD.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `dataServer.class` | enum | `""` | One of `"x-small", "small"`, `"medium"`, `"large", "x-large"`. Overrides the value of `class` only for the Data Service component. Used to scale Data Service independently of other platform components (for example for sites with higher or lower Data Fabric usage).Changing `dataServer.class` after an initial deployment will not automatically affect all sizings driven by it (e.g. disk volume sizes will not change). **This field is immutable.**See [T-Shirt Sizes](#t-shirt-sizing). | false | Multiple fields across all components. |
| `dataServer.rts.count` | int | `nil` | Override the RTS count set by `class`. *Updating this field requires restarting both Data Service's and Webapp's pods.* See [Real-time Store](https://docs.appian.com/suite/help/latest/Data_Server.html#real-time-store) and [Configuring the Data Service](https://docs.appian.com/suite/help/latest/Configuring_the_Data_Server.html) for more info. | false | `spec.dataServer.topology.rtsCount` |
| `dataServer.rts``.threads` | int | `nil` | Override the value of the custom property `ads.adb.systemConfig__.rts.threads`. This property is automatically defaulted in line with the chosen class's default RTS count. Only use this field to override the built-in default. See [Configuring the real-time store](https://docs.appian.com/suite/help/latest/Configuring_the_Data_Server.html#configuring-the-real-time-store) for guidance. | false | `spec.customProperties``.ads.adb.systemConfig__.rts.threads` |
| `dataServer.rts``.memoryLimit` | string | `""` | Override the value of the custom property `ads.adb.systemConfig__.rts.memory_limit`. This property is automatically defaulted in line with the chosen class's default RTS count. Only use this field to override the built-in default. See [Configuring the real-time store](https://docs.appian.com/suite/help/latest/Configuring_the_Data_Server.html#configuring-the-real-time-store) for guidance. | false | `spec.customProperties``.ads.adb.systemConfig__.rts.memory_limit` |
| `dataServer.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.dataServer``.volumeClaimTemplateSpec.resources``.requests.storage` |
| `dataServer.resources.requests.cpu` | int or string | `""` | Override the component's CPU requests set by `class`. | false | `spec.dataServer``.resources.requests.cpu` |
| `dataServer.resources.limits.cpu` | int or string | `""` | Override the component's CPU limits set by `class`. | false | `spec.dataServer``.resources.limits.cpu` |
| `dataServer.resources.requests.memory` | int or string | `""` | Override the component's memory requests set by `class`. | false | `spec.dataServer``.resources.requests.memory` |
| `dataServer.resources.limits.memory` | int or string | `""` | Override the component's memory limits set by `class`. | false | `spec.dataServer``.resources.limits.memory` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Service Manager



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `serviceManager.replicas` | int | `nil` | Override the number of replicas for service manager set by `highAvailability`. Defaults to `1` for non-high availability and `3` for high availability. *Updating this field is disallowed both before Appian has started and when `highAvailability` is not `true`.* | false | `spec.serviceManager.replicas` |
| `serviceManager.komodoDirectMemMax` | string | `""` | Override the environment variable `KOMODO_DIRECT_MEM_MAX` set by `class`. | false | `spec.serviceManager.env` |
| `serviceManager.komodoHeapMax` | string | `""` | Override the environment variable `KOMODO_HEAP_MAX` set by `class`. | false | `spec.serviceManager.env` |
| `serviceManager.maxExecEngineLoadMetric` | int | `120` | Override the value of the custom property `server.conf.processcommon.MAX_EXEC_ENGINE_LOAD_METRIC`. This property is defaulted to `120`. | false | `spec.customProperties``.server.conf.processcommon.MAX_EXEC_ENGINE_LOAD_METRIC` |
| `serviceManager.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.serviceManager``.volumeClaimTemplateSpec.resources``.requests.storage` |
| `serviceManager.analyticsExecShardCount` | int | `3` | Override the number of shards of the process analytics and process execution engines. **This field is immutable.** See [Add Execution and Analytics Shards](https://docs.appian.com/suite/help/latest/Scaling_Appian.html#add-execution-and-analytics-shards) for more info. | false | `spec.serviceManager``.topology.analyticsExecShardCount` |
| `serviceManager.exec.resources.requests.cpu` | int or string | `""` | Override the execution engines' CPU requests set by `class`. | false | `spec.serviceManager``.engineOverrides.execution``.resources.requests.cpu` |
| `serviceManager.exec.resources.limits.cpu` | int or string | `""` | Override the execution engines' CPU limits set by `class`. | false | `spec.serviceManager``.engineOverrides.execution``.resources.requests.cpu` |
| `serviceManager.exec.resources.requests.memory` | int or string | `""` | Override the execution engines' memory requests set by `class`. | false | `spec.serviceManager``.engineOverrides.execution``.resources.requests.memory` |
| `serviceManager.exec.resources.limits.memory` | int or string | `""` | Override the execution engines' memory limits set by `class`. | false | `spec.serviceManager``.engineOverrides.execution``.resources.limits.memory` |
| `serviceManager.analytics.resources.requests.cpu` | int or string | `""` | Override the analytics engines' CPU requests set by `class`. | false | `spec.serviceManager``.engineOverrides.analytics``.resources.requests.cpu` |
| `serviceManager.analytics.resources.limits.cpu` | int or string | `""` | Override the analytics engines' CPU limits set by `class`. | false | `spec.serviceManager``.engineOverrides.analytics``.resources.requests.cpu` |
| `serviceManager.analytics.resources.requests.memory` | int or string | `""` | Override the analytics engines' memory requests set by `class`. | false | `spec.serviceManager``.engineOverrides.analytics``.resources.requests.memory` |
| `serviceManager.analytics.resources.limits.memory` | int or string | `""` | Override the analytics engines' memory limits set by `class`. | false | `spec.serviceManager``.engineOverrides.analytics``.resources.limits.memory` |
| `serviceManager.tier2.resources.requests.cpu` | int or string | `""` | Override the CPU requests for the groups, collaboration and process design engines set by `class`. | false | `spec.serviceManager``.engineOverrides.[groups|content|processDesign]``.resources.requests.cpu` |
| `serviceManager.tier2.resources.limits.cpu` | int or string | `""` | Override the CPU limits for the groups, collaboration and process design engines set by `class`. | false | `spec.serviceManager``.engineOverrides.[groups|content|processDesign]``.resources.requests.cpu` |
| `serviceManager.tier2.resources.requests.memory` | int or string | `""` | Override the memory requests for the groups, collaboration and process design engines set by `class`. | false | `spec.serviceManager``.engineOverrides.[groups|content|processDesign]``.resources.requests.memory` |
| `serviceManager.tier2.resources.limits.memory` | int or string | `""` | Override the the memory limits for the groups, collaboration and process design engines set by `class`. | false | `spec.serviceManager``.engineOverrides.[groups|content|processDesign]``.resources.limits.memory` |
| `serviceManager.default.resources.requests.cpu` | int or string | `""` | Override the default CPU requests used by all other engines set by `class`. | false | `spec.serviceManager``.resources.requests.cpu` |
| `serviceManager.default.resources.limits.cpu` | int or string | `""` | Override the default CPU limits used by all other engines set by `class`. | false | `spec.serviceManager``.resources.limits.cpu` |
| `serviceManager.default.resources.requests.memory` | int or string | `""` | Override the default memory requests used by all other engines set by `class`. | false | `spec.serviceManager``.resources.requests.memory` |
| `serviceManager.default.resources.limits.memory` | int or string | `""` | Override the the memory limits used by all other engines set by `class`. | false | `spec.serviceManager``.resources.limits.memory` |
| `serviceManager.engineOverrides` | object | `{}` | Allows complete override of all per-engine configurations set by `class`. Used in the scenario where you require complete granular control over every engine type's CPU and memory configuration. To set the `engineOverrides` field for the first time, generate the CR spec without `engineOverrides` set using `helm template` and then use the output value of `engineOverrides` in the generated CR spec as the starting value for your Helm values `engineOverrides` field. This way, you start with the current engine-level configurations for your chosen class and can adjust them accordingly.See [Engine Overrides](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1engineoverrides) for more info. | false | `spec.serviceManager.engineOverrides` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Webapp



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `webapp.replicas` | int | `nil` | Override the number of replicas for webapp set by `highAvailability`. When set, this field also sets the httpd component's replicas to match. *Updating this field is disallowed both before Appian has started and when `highAvailability` is not `true`.* | false | `spec.webapp.replicas``spec.httpd.replicas` |
| `webapp.minHeap` | string | `""` | Set the custom property `conf.appserver.minHeapSize`. | false | `spec.customProperties` |
| `webapp.maxHeap` | string | `""` | Override the custom property `conf.appserver.maxHeapSize` set by `class`. | false | `spec.customProperties` |
| `webapp.autodeleteArchivesDelayDays` | string | `"30"` | Override the custom property `server.conf.processcommon.AUTODELETE_ARCHIVES_DELAY_DAYS` set automatically by the chart. This [setting](https://docs.appian.com/suite/help/latest/Configuring_Archived_Processes.html#automated-deletion) defines when archived processes will automatically be deleted, both from the Process Activity monitor view, and the .l files themselves. | false | `spec.customProperties` |
| `webapp.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.webapp``.volumeClaimTemplateSpec.resources``.requests.storage` |
| `webapp.resources.requests.cpu` | int or string | `""` | Override the component's CPU requests set by `class`. | false | `spec.webapp``.resources.requests.cpu` |
| `webapp.resources.limits.cpu` | int or string | `""` | Override the component's CPU limits set by `class`. | false | `spec.webapp``.resources.limits.cpu` |
| `webapp.resources.requests.memory` | int or string | `""` | Override the component's memory requests set by `class`. | false | `spec.webapp``.resources.requests.memory` |
| `webapp.resources.limits.memory` | int or string | `""` | Override the component's memory limits set by `class`. | false | `spec.webapp``.resources.limits.memory` |
| `webapp.dataSources` | object | `{}` | Override completely the webapp data source configuration set via templates by `dataSources.primary` and `dataSources.business`. | false | `spec.webapp.dataSources` |
| `webapp.additionalInitContainers` | list | `[]` | A list of initialization containers belonging to the component to deploy in addition to any default init containers configured by the chart. If no default init containers would be deployed, this field has the same effect as `webapp.initContainers`. *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Init Containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) for more info. | false | `spec.webapp.initContainers` |
| `webapp.customLoggers` | [Custom Logger](#custom-logger) list | `[]` | A list of [Custom Logger](#custom-logger) to be applied to webapp components. Implements the [Customizing Application Logging](https://docs.appian.com/suite/help/latest/customizing-application-logging.html#customizing-application-logging-for-the-first-time) pattern. If set, this chart deploys an additional ConfigMap `appian-log4j-override-properties` and mounts it to all webapp pods. | false | `spec.webapp.additionalVolumes``spec.webapp.additionalVolumeMounts` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Httpd



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `httpd.replicas` | int | `nil` | Override the number of replicas for httpd set by `highAvailability` or `webapp.replicas`. | false | `spec.httpd.replicas` |
| `httpd.resources.requests.cpu` | int or string | `""` | Override the component's CPU requests set by `class`. | false | `spec.httpd``.resources.requests.cpu` |
| `httpd.resources.limits.cpu` | int or string | `""` | Override the component's CPU limits set by `class`. | false | `spec.httpd``.resources.limits.cpu` |
| `httpd.resources.requests.memory` | int or string | `""` | Override the component's memory requests set by `class`. | false | `spec.httpd``.resources.requests.memory` |
| `httpd.resources.limits.memory` | int or string | `""` | Override the component's memory limits set by `class`. | false | `spec.httpd``.resources.limits.memory` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### MirrorMaker



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `mirrorMaker.resources` | object | `{}` | Compute resources required by the component's container(s). See [Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) for more info. | false | `spec.mirrorMaker.resources` |
| `mirrorMaker.sourceBrokers` | list | `[]` | Override the value set by `replication.mirrorMaker.listeners`. List of hosts that point to the Kafka brokers in the source cluster. *Updating this field requires restarting MirrorMaker's pod(s).* | false | `spec.mirrorMaker.sourceBrokers` |
| `mirrorMaker.storageSize` | string | `""` | Override the size of the component's RWO volumes set by `class`. Changing this value after an initial deployment will not automatically resize the volumes. **This field is immutable.** | false | `spec.mirrorMaker``.volumeClaimTemplateSpec.resources``.requests.storage` |
| [Common Additional Parameters](#common-additional-parameters) |  |  | (Members of [Common Additional Parameters](#common-additional-parameters) are embedded into this type) |  |  |

#### Common Additional Parameters

The following optional parameters can be specified for any component listed [above](#per-component-overrides-and-additional-parameters).



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `[component].initContainers` | list | `[]` | A list of initialization containers belonging to the component. Initialization containers satisfy a variety of use cases - including supplying RDBMS/JDBC drivers. *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Init Containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) for more info. For a component that has a `[component].additionalInitContainers` parameter, `[component].initContainers` will override any init containers that are automatically configured by the chart. | false | `spec.[component].initContainers` |
| `[component].env` | list | `[]` | A list of environment variables to set in the component's container(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Define Environment Variables for a Container](https://kubernetes.io/docs/tasks/inject-data-application/define-environment-variable-container/) for more info. | false | `spec.[component].env` |
| `[component].additionalVolumes` | list | `[]` | Additional volumes for the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Volumes](https://kubernetes.io/docs/concepts/storage/volumes/) for more info. | false | `spec.[component].additionalVolumes` |
| `[component].additionalVolumeMounts` | list | `[]` | Additional volume mounts for the component's container(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Volumes](https://kubernetes.io/docs/concepts/storage/volumes/) for more info. | false | `spec.[component].additionalVolumeMounts` |
| `[component].sidecarContainers` | list | `[]` | Sidecar containers for the component's container(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* | false | `spec.[component].sidecarContainers` |
| `[component].nodeSelector` | object | `{}` | A selector which must be true for the component's pod(s) to fit on a node. *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [nodeSelector](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector) for more info. | false | `spec.[component].nodeSelector` |
| `[component].tolerations` | list | `[]` | Tolerations for the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Taints and Tolerations](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/) for more info. | false | `spec.[component].tolerations` |
| `[component].additionalNetworkPolicyIngressRules` | list | `[]` | Additional ingress rules for the component's network policy. **Forbidden when `spec.networkPolicies.enabled` is `false`.** See [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/#the-networkpolicy-resource) for more info. | false | `spec.[component].additionalNetworkPolicyIngressRules` |
| `[component].priorityClassName` | string | `""` | Priority Class for the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* See [Pod Priority and Preemption](https://kubernetes.io/docs/concepts/scheduling-eviction/pod-priority-preemption/) for more info. | false | `spec.[component].priorityClassName` |
| `[component].dnsPolicy` | object | `""` | DNS policy for the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* This field will default to `ClusterFirst` if not specified. See [Pod DNS Policy](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/#pod-s-dns-policy) for more info. | false | `spec.[component].dnsPolicy` |
| `[component].dnsConfig` | object | `{}` | DNS Config for the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* This field is required when DNSPolicy is set to `None`. If DNS Policy is not specified, then `ClusterFirst` is used. See [Pod DNS Config](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/#pod-dns-config) for more info. | false | `spec.[component].dnsConfig` |
| `[component].podAnnotations` | map[string]string | `{}` | Annotations to be applied to the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* | false | `spec.[component].podAnnotations` |
| `[component].podLabels` | map[string]string | `{}` | Labels to be applied to the component's pod(s). *For stateful components with a single replica, updating this field requires restarting the component's pod.* | false | `spec.[component].podLabels` |
| `[component].serviceAccount` | object | `{}` | Configuration for the component's [service account](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1serviceaccount). | false | `spec.[component].serviceAccount` |
| `[component].securityContext` | object | `{}` | Container-level security context for the component. Overrides the global `securityContext`. Passthrough to [`corev1.SecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#securitycontext-v1-core). | false | `spec.[component].securityContext` |
| `[component].podSecurityContext` | object | `{}` | Pod-level security context for the component. Overrides the global `podSecurityContext`. Passthrough to [`corev1.PodSecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#podsecuritycontext-v1-core). Requires Appian Operator v0.200.0+. | false | `spec.[component].podSecurityContext` |

#### Custom Logger

The following parameters are available for each item in the list `webapp.customLoggers`. The chart's Custom Logger Template makes it simpler to customize application logging. Logging for these custom loggers will be output in the root `~/logs` directory of each pod and named `{reference}.log`. Log rotation is enabled within the settings output in the ConfigMap generated by this chart.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `reference` | string | `""` | An uppercase underscore separated reference for your logger, containing letters only (e.g. `COM_APPIAN_PACKAGE_DEBUG`). | true | `appian-log4j-override-properties` |
| `packageName` | string | `""` | The package name to be logged (e.g. `com.appian.package`). Do not include the prefix `log4j.logger.` in the package name provided. | true | `appian-log4j-override-properties` |
| `loggingLevel` | string | `""` | The logging level to be logged (e.g. `DEBUG`). | true | `appian-log4j-override-properties` |

#### Service

By default, a `service` is configured by the chart with `spec.service.type: ClusterIP`. Configure this `service` object for any alternative service configurations.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `service` | object | `{}` | Service defines configuration for creating Appian's service resource. See [Service](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1service) for more info. | false | `spec.service` |

#### Ingress

Ingress for ingress controllers [NGINX Ingress Controller](https://docs.nginx.com/nginx-ingress-controller/), [AWS Load Balancer Controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller) and [Azure Application Gateway Ingress Controller (AGIC)](https://learn.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview) can be configured via [ingressTemplate](#ingress-template-parameters). For any other ingress controller, use `ingress` below.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `ingress` | object | `{}` | Configuration for creating Appian's ingress resource if not using [ingressTemplate](#ingress-template-parameters). See [Ingress](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1ingress) for more info. | false | `spec.ingress` |

#### RPA

RPA can be configured for the Appian site via the `rpa` component. No pre-configured options are included in this Helm chart for RPA at this time. See the [sample YAML file](https://docs.appian.com/suite/help/latest/k8s/install-appian-on-k8s.html#4.-create-an-appian-yaml-file), the [Custom Resource Definition](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1.rpa) and the [RPA Setup section](https://docs.appian.com/suite/help/latest/rpa-setup-on-k8s.html) for RPA configuration options.



| Key | Type | Default | Description | Required | CRD Field(s) Impacted |
| --- | --- | --- | --- | --- | --- |
| `rpa` | object | `{}` | Defines configuration for RPA. See [RPA](https://docs.appian.com/suite/help/latest/k8s/crds.html#v1beta1.rpa) for more info. | false | `spec.service` |

### Managed Custom Properties

The following custom properties are automatically added based on either default configurations, class or driven by values file fields.



| Component | Custom Properties | Driven By |
| --- | --- | --- |
| App Server Heap | `conf.appserver.maxHeapSize` | Class and `webapp` override field |
| App Server Heap | `conf.appserver.minHeapSize` | `webapp` field |
| SMTP | `conf.mailhandler.*` properties, `conf.suite.MAIL_SCHEME` and `conf.suite.MAIL_SERVER_AND_PORT` | `smtp` fields |
| Data Service | `ads.adb.systemConfig__.rts.memory_limit` and `ads.adb.systemConfig__.rts.threads` | Class and `dataServer` override field |
| Process Engines | `server.conf.processcommon.MAX_EXEC_ENGINE_LOAD_METRIC` | Default value and `serviceManager` override field |
| Process Engines | `server.conf.processcommon.AUTODELETE_ARCHIVES_DELAY_DAYS` | Default value and `webapp` override field |
| Metrics API | `appian.feature.selfManagedMonitoring` and `metricsauthtoken` | `metricsAuthToken` field |

### Excluded Appian CRD Fields

The following fields from the Appian CRD either cannot be set via this Helm chart, or the value that this Helm chart configures cannot be directly overridden. If you must customise one of these fields, this can be done in the site YAML directly after generating it via `helm template`.



| CRD Field | Reason |
| --- | --- |
| `[component].podDisruptionBudget` | Pod Disruption Budgets are set by the chart for each component when `highAvailability` is `true`. |
| `[component].replicas` | `[component].replicas`is set by the chart depending on the value of `highAvailability`. For service manager, webapp and httpd this value can be overridden. For all other components this value cannot be overridden and will be `1` for non-HA and `3` for HA). |
| `[component].affinity` | The Appian operator deploys a default affinity configuration. This cannot be customized for the Service Manager pods without breaking exec/analytics engine shard-level affinity configuration. This chart does not support customizing affinity. This chart does, however, deploy a customised affinity rule for httpd to allow the additional httpd pod that is deployed and terminated on site startup to be scheduled on the same worker as another httpd pod to ensure it can launch and terminate successfully. `nodeSelector` can still be configured globally and per-component to constrain Pods to nodes with specific labels. |
| `serviceManager.engineOverrides.[engine].replicas` | Engine type replica count cannot be customised at engine level. They will always use the global `serviceManager.replicas` value. |

## Release Notes

#### 2.1.0

**BREAKING CHANGES** This release includes breaking changes. If upgrading to this version, read these Release Notes carefully before upgrading and use `helm template` to compare the output with that from your current version to ensure the result is as expected.

* The minimum Appian Operator version compatible with this chart is v0.200.0.


* **Breaking Change** `securityContext` is now a pure passthrough to [`corev1.SecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#securitycontext-v1-core) (container-level), aligning with the Appian Operator v0.200.0+ CRD. If you previously set `fsGroup` or `fsGroupChangePolicy` under `securityContext` (globally or per-component), you must move these to `podSecurityContext`. These fields are [deprecated on `securityContext`](https://docs.appian.com/suite/help/latest/k8s-0.201.0/crds.html#v1beta1securitycontext) and will be removed by the operator in a future release.


* New `podSecurityContext` field added as a pure passthrough to [`corev1.PodSecurityContext`](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.35/#podsecuritycontext-v1-core) (pod-level). Supports global and per-component override, same pattern as `securityContext` and `nodeSelector`.



**Migration example** — if your current values contain:


```

```
xxxxxxxxxx
```

```
# Old (pre-2.1.0)
```

```
securityContext:
```

```
 runAsUser: 500
```

```
 fsGroup: 500
```

```
 fsGroupChangePolicy: OnRootMismatch
```

```
Update to:


```

```
xxxxxxxxxx
```

```
# New (2.1.0+)
```

```
securityContext:
```

```
 runAsUser: 500
```

```
 allowPrivilegeEscalation: false
```

```
podSecurityContext:
```

```
 fsGroup: 500
```

```
 fsGroupChangePolicy: OnRootMismatch
```

```
The same applies at component level — e.g. `httpd.securityContext.fsGroup` becomes `httpd.podSecurityContext.fsGroup`.

#### 2.0.0

**BREAKING CHANGES** This release includes breaking changes. If upgrading to this version, read these Release Notes carefully before upgrading and use `helm tempalate` to compare the output with that from your current version to ensure the result is as expected.

* The minimum Appian Operator version compatible with this chart is v0.194.0.


* Corrected data source template for Oracle so the connection URL includes the required leading `//` after the `@`.


* Support setting `securityContext` globally for all components, or at component level as `[component].securityContext`.


* Support disabling the built-in Search Server init container that sets vm.max\_map\_count on the worker node via the new field `searchServer.setVmMaxMapCount`. This field defaults to `true`. If you choose to disable this init container, you must ensure via other means that vm.max\_map\_count is correctly set on all worker nodes onto which Search Server pods could be provisioned.


* Support setting `images.pullPolicy` to be applied to all components and built-in init containers.


* Removed support for deprecated `dataSources.mysqlDriverConfigMapName` field.


* Added default CPU and memory requests and limits to httpd. Default httpd resources can be overridden in the same way as other components (instead of via the removed field `httpd.resources`).


* httpd affinity rules updated to allow the n+1 httpd pod that is launched to run on the same worker as another pod if required, to ensure it is able to run and terminate. This avoids being left with a stuck httpd pod when httpd replica count is <= number of worker nodes.


* Support setting `spec.[component].serviceAccount` field for a component.


* The chart sets the custom property `server.conf.processcommon.AUTODELETE_ARCHIVES_DELAY_DAYS` to a default of 30 days to automatically clean up archived processes. This can be customised via `webapp.autodeleteArchivesDelayDays`. If not customised, this will now result in your archived processes being automatically deleted after 30 days.


* Support OpenShift Default ingress controller as `ingressTemplate`.


* Chart now sets the new custom properties used by the Appian Data Service since 25.1 `ads.adb.systemConfig__.rts.memory_limit` and `ads.adb.systemConfig__.rts.threads`, instead of the deprecated `rts.queryMemoryLimits.circuitBreaker.threshold.bytes`. Removed corresponding override field `dataServer.rts.queryMemoryCircuitBreakerThresholdBytes` and added new override fields under `dataServer.rts`.


* Restructured or renamed some existing chart values fields to align with a more standardised naming approach (see table below).


* The chart no longer populates `spec.httpd.nslookupImage` (which is not used from Operator v0.194.0).


* Data source username field `dataSources.[primary\|business[]].username` has been removed in favour of providing the username(s) via a secret `dataSources.[primary\|business[]].usernameSecretKeyRef`.



**Values field restructuring**

Some of the fields have been restructured in this release to be more user friendly. The following table provides a guide to help you update your values files to use the new field name.



| Old Field Name | New Field Name | Notes |
| --- | --- | --- |
| `[component].cpuRequests` | `[component].resources.requests.cpu` |  |
| `[component].cpuLimits` | `[component].resources.limits.cpu` |  |
| `[component].memoryRequests` | `[component].resources.requests.memory` |  |
| `[component].memoryLimits` | `[component].resources.limits.memory` |  |
| `disableCpuLimits` | `enableCpuLimits` | Default functionality is unchanged. CPU limits are disabled by default. |
| `disableResourceRequests` | `enableResourceRequests` | Default functionality is unchanged. Resource requests are enabled by default. |
| `webapp.minHeapSize` | `webapp.minHeap` |  |
| `webapp.maxHeapSize` | `webapp.maxHeap` |  |
| `tshirtSize` | `class` |  |
| `images.imagePullSecrets` | `images.pullSecrets` |  |
| `k3LicSecretName` | `license.k3SecretName` |  |
| `k4LicSecretName` | `license.k4SecretName` |  |
| `appianLicConfigMapName` | `license.appianConfigMapName` |  |
| `dataSources.mysqlDriverConfigMapName` | Removed | Removed. MySQL driver is now too large to support deployment via ConfigMap |
| `dataServer.rts.queryMemoryCircuitBreakerThresholdBytes` | Removed | Removed. From 25.1 the Data Service uses alternative custom properties instead, defaulted based on class and overridden via `dataServer.rts.threads` and `dataServer.rts.memoryLimit`. |
| `dataSources.[primary\|business[]].username` | `dataSources.[primary\|business[]].usernameSecretKeyRef.name` and `dataSources.[primary\|business[]].usernameSecretKeyRef.key` | Data Source Template's `username` field has been removed in favour of providing the username(s) via a secret. |
| `ingressTemplate.healthcheckIntervalSeconds` | `ingressTemplate.healthcheck.intervalSeconds` |  |
| `ingressTemplate.healthcheckPath` | `ingressTemplate.healthcheck.path` |  |
| `ingressTemplate.healthcheckPort` | `ingressTemplate.healthcheck.port` |  |
| `ingressTemplate.healthcheckProtocol` | `ingressTemplate.healthcheck.protocol` |  |
| `ingressTemplate.healthcheckTimeoutSeconds` | `ingressTemplate.healthcheck.timeoutSeconds` |  |
| `ingressTemplate.healthcheckHealthyThresholdCount` | `ingressTemplate.healthcheck.healthyThresholdCount` |  |
| `ingressTemplate.healthcheckUnhealthyThresholdCount` | `ingressTemplate.healthcheck.unhealthyThresholdCount` |  |


*Built against Appian operator v0.194.0 and Appian platform 25.4. This chart will work with older and newer versions of the Appian operator (to a minimum of v0.194.0) and Appian platform, but some parameters may not be valid.*

#### 1.2.0

* Removed `searchServerPassword` field. From Operator v0.181.0, and Appian platform versions hotfixed from July 03, 2025 or later, the Operator now manages the Search Server password for you. Manually specifying a Search Server password is no longer required nor recommended. If you previously configured a Search Server password, you must remove this from your `passwords.properties` file when upgrading to this version of the Helm chart (see [this KB](https://community.appian.com/support/w/kb/3582/kb-2322-application-server-fails-to-start-due-to-improperly-configured-search-server-credentials#:~:text=number%20of%20replicas.-,Operator%20v0.181.0%20and%20Later,-The%20following%20assumes) for more details).



*Built against Appian operator v0.181.0 and Appian platform 25.3. This chart will work with older and newer versions of the Appian operator (to a minimum of v0.181.0) and Appian platform, but some parameters may not be valid.*

#### 1.1.3

* Fixed Search Server CPU requests for Medium t-shirt size to 200m.



*Built against Appian operator v0.178.0 and Appian platform 25.3. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

#### 1.1.2

* Fixed issue where setting `disableResourceRequests: true` removed resource requests altogether but left limits in place, resulting in Kubernetes automatically adding resource requests back in and set to the same values as the limits. Now, setting `disableResourceRequests: true` sets resource requests to `0` to prevent this.



*Built against Appian operator v0.173.0 and Appian platform 25.1. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum operator version tested with this Helm chart is v0.159.0.*

#### 1.1.1

* Fixed issue where `webapp.engineOverrides` field could not be set as it was incorrectly defined as an array instead of an object.


* Support setting `webapp.minHeapSize` to configure webapp's minimum heap size instead of using `customProperties`.



*Built against Appian operator v0.173.0 and Appian platform 25.1. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum operator version tested with this Helm chart is v0.159.0.*

#### 1.1.0

* Minor increase to Search Server CPU requests for Small and Medium t-shirt sizes in-line with public docs update.


* Added `dataServer.class` field to enable independent scaling of the Data Service component without changing global t-shirt size.


* **Breaking Change** Aligned Data Service t-shirt sizing with latest public docs. This keeps resources relatively similar to earlier versions, but reduces RTS count for each t-shirt size. Use the new `dataServer.class` field or the `dataServer.rts.count` field to readjust if required.


* **Breaking Change** CPU limits are no longer set by default. This is to align with K8s best practices (where accurate CPU limits for the specific usage scenario are not already known). CPU limits can be applied by setting the new field `disableCpuLimits` to `false` (it defaults to `true`). If enabled, the t-shirt size's CPU limits are applied. This can be overridden globally by setting the new field `defaultCpuLimits` or overridden per component by setting `[component].cpuLimits`. The field `workerNodeTotalCpu` has been removed in favour of `defaultCpuLimits`. Previous chart behaviour can be achieved by setting `disableCpuLimits` to `false` and setting `defaultCpuLimits` to the previous value of `workerNodeTotalCpu`.


* **Breaking Change** Removed `serviceManager.cpuLimits` and `serviceManager.memoryLimits` fields. Use `serviceManager.default.cpuLimits` and `serviceManager.default.memoryLimits` instead.


* `disableResourceRequests` now sets no `resources.requests` at all, rather than incorrectly setting them to `0`.


* Deprecated `dataSources.mysqlDriverConfigMapName`, which enabled deploying the MySQL driver via a ConfigMap and webapp init container. The supported MySQL driver is now too large to be mounted via a ConfigMap. This field will be removed in a future version.


* Fixed broken public docs links



*Built against Appian operator v0.173.0 and Appian platform 25.1. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum operator version tested with this Helm chart is v0.159.0.*

#### 1.0.3

* Fixed an issue with the AGIC Ingress Template where an invalid `ingressClassName` was set. It now sets the annotation `kubernetes.io/ingress.class` instead, to the correct value, instead of setting `ingressClassName`.


* AGIC Ingress Template now defaults `ingressTemplate.usePrivateIp` to `false` instead of `true`.



*Built against Appian operator v0.166.0 and Appian platform 24.4. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 1.0.2

* Allow `storage.haSharedData` to be specified when not in a high availability configuration


* No longer enforces `passwordsPropertiesSecretName` to be set (as this need only be provided and loaded at first environment startup)


* Support override of `serviceManager.replicas` in high availability configurations (from the default `3`)



*Built against Appian operator v0.166.0 and Appian platform 24.4. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 1.0.1

* Fixed bug preventing `ingress` from being used to completely override the templated ingress `ingressTemplate`



*Built against Appian operator v0.166.0 and Appian platform 24.4. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 1.0.0

* Fixed bug preventing `webapp.dataSources` from being used to completely override the templated data sources `dataSources.primary` and `dataSources.business`


* Fixed bug where CPU and memory limits were not set for execution, analytics, groups, collaboration and process design engines when applying t-shirt sizes


* Default value of the Data Service custom property `rts.queryMemoryLimits.circuitBreaker.threshold.bytes` automatically set based on RTS count


* Added `webapp.customLoggers` to facilitate the addition of customized application logging


* Added `metricsAuthToken` to enable Appian Self-Managed Monitoring metrics API


* Added `cascadeVersionToComponentTags` for compatibility with the Appian Migration Tool


* Built-in SMTP-related custom properties are only added by the chart if `smtp.host` is provided


* `serviceManager.maxExecEngineLoadMetric` is now an integer (corrected from string)


* `dataServer.rts.count` is now an integer (corrected from string)


* `dataServer.rts.queryMemoryCircuitBreakerThresholdBytes` is now an integer (corrected from string)



*Built against Appian operator v0.166.0 and Appian platform 24.4. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.159.0.*

#### 0.1.2

* Added `disableResourceRequests` for running on smaller, dedicated worker nodes



*Built against Appian operator v0.161.0 and Appian platform 24.3. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is v0.156.0.*

#### 0.1.1

* Supports new Search Server API password (introduced in 24.3)


* Minor bug fixes



*Built against Appian operator v0.161.0 and Appian platform 24.3. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

*Minimum supported operator version is now v0.156.0.*

#### 0.1.0

First public release.

*Built against Appian operator v0.156.0 and Appian platform 24.1. This chart will work with other versions of the Appian operator and platform, both older and newer, but some parameters may not be valid (e.g. `spec.rpa` was only introduced from v0.156.0).*

## License

Appian AppMarket (see [here](https://community.appian.com/p/appmarket-faq#:~:text=How%20are%20Free%20Apps%20supported%3F))



