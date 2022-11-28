<!--
author:   André Dietrich

email:    LiaScript@web.de

version:  0.0.1

language: en

narrator: US English Female

comment:  This plugin removes the nav-bar in fullscreen-mode, which can be used in presentations.

@onload

window.onresize = function (event) {
    var maxHeight = window.screen.height,
        maxWidth = window.screen.width,
        curHeight = window.innerHeight,
        curWidth = window.innerWidth;

    if (maxWidth == curWidth && maxHeight == curHeight) {
        const head = document.getElementById("lia-toolbar-nav")
        
        head.style.display="none"
        head.nextSibling.style["margin-top"] = "0px"

        window.fullscreenMode = true
    } else if (window.fullscreenMode){
        const head = document.getElementById("lia-toolbar-nav")
        
        head.style.display=""
        head.nextSibling.style["margin-top"] = ""

        window.fullscreenMode = false
    }
}

@end
-->

# Fullscreen - Template

By importing this README via:

`import: https://raw.githubusercontent.com/LiaTemplates/Fullscreen/main/README.md`

into your document, an event listener will be added automatically to your course, which will hide the main nav bar of your course when you get into fullscreen mode by hitting <kbd>F11</kbd>.

## Implementation

``` javascript
@onload

window.onresize = function (event) {
    var maxHeight = window.screen.height,
        maxWidth = window.screen.width,
        curHeight = window.innerHeight,
        curWidth = window.innerWidth;

    if (maxWidth == curWidth && maxHeight == curHeight) {
        const head = document.getElementById("lia-toolbar-nav")
        
        head.style.display="none"
        head.nextSibling.style["margin-top"] = "0px"

        window.fullscreenMode = true
    } else if (window.fullscreenMode){
        const head = document.getElementById("lia-toolbar-nav")
        
        head.style.display=""
        head.nextSibling.style["margin-top"] = ""

        window.fullscreenMode = false
    }
}

@end
```