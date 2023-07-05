# Welcome my study archive

## 自定义

单击搜素框旁的按钮切换亮色或暗色。

单击以下按钮设置你所喜欢的网页主题色。

<div class=mdx-switch> 
    <button data-md-color-primary=red><code data-md-color-primary=red>red</code></button> 
    <button data-md-color-primary=pink><code data-md-color-primary=pink>pink</code></button> 
    <button data-md-color-primary=purple><code data-md-color-primary=purple>purple</code></button> 
    <button data-md-color-primary=deep-purple><code data-md-color-primary=deep-purple>deep purple</code></button> 
    <button data-md-color-primary=indigo><code data-md-color-primary=indigo>indigo</code></button>
    <button data-md-color-primary=blue><code data-md-color-primary=blue>blue</code></button> 
    <button data-md-color-primary=light-blue><code data-md-color-primary=light-blue>light blue</code></button>
    <button data-md-color-primary=cyan><code data-md-color-primary=cyan>cyan</code></button> 
    <button data-md-color-primary=teal><code data-md-color-primary=teal>teal</code></button>
    <button data-md-color-primary=green><code data-md-color-primary=green>green</code></button> 
    <button data-md-color-primary=light-green><code data-md-color-primary=light-green>light green</code></button> 
    <button data-md-color-primary=lime><code data-md-color-primary=lime>lime</code></button>
    <button data-md-color-primary=yellow><code data-md-color-primary=yellow>yellow</code></button> 
    <button data-md-color-primary=amber><code data-md-color-primary=amber>amber</code></button> 
    <button data-md-color-primary=orange><code data-md-color-primary=orange>orange</code></button> 
    <button data-md-color-primary=deep-orange><code data-md-color-primary=deep-orange>deep orange</code></button> 
    <button data-md-color-primary=brown><code data-md-color-primary=brown>brown</code></button> 
    <button data-md-color-primary=grey><code data-md-color-primary=grey>grey*</code></button> 
    <button data-md-color-primary=blue-grey><code data-md-color-primary=blue-grey>blue grey*</code></button> 
    <button data-md-color-primary=black><code data-md-color-primary=black>black*</code></button>
</div>

!!! warning "*"
    
    这三个颜色并不是构架所支持的颜色，我做了简单的调整但是依旧不太好看

<script>
    var buttons = document.querySelectorAll("button[data-md-color-primary]");
    Array.prototype.forEach.call(buttons, function(button) {
        button.addEventListener("click", function() {
            document.body.dataset.mdColorPrimary = this.dataset.mdColorPrimary;
            document.body.dataset.mdColorAccent = this.dataset.mdColorPrimary;
            localStorage.setItem("data-md-color-primary", this.dataset.mdColorPrimary);
            localStorage.setItem("data-md-color-accent", this.dataset.mdColorPrimary);
        })
    })
</script>