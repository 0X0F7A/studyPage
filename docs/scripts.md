# 更整洁的bilibili
```css
/* ==UserStyle==
@name           2023/5/17 09:53:09
@namespace      github.com/openstyles/stylus
@version        1.0.0
@description    A new userstyle
@author         Me
==/UserStyle== */

@-moz-document domain("www.bilibili.com") {
    .relative-container, .recommended-swipe-core, .bili-grid, .eva-banner, .vip-wrap, .ad-report:not(:empty), .video-card-ad-small, .recommended-swipe, .primary-btn.go-back, .link-item.link-item__right, .other-link, .footer-icons, .pop-live-small-mode，
     .red-num--dyn, .pop-live-small-mode, #bili-header-banner-img, .red-num--dynamic{
        display:none !important;
    }
    .bili-grid.short-margin.grid-anchor{
        display:flex !important;
        width: 80%;
        left: 150px;
    }
    .recommend-container__2-line > :nth-of-type(n+10) {
        display:flex !important;
    }
    input::-webkit-input-placeholder, input::-moz-placeholder, input:-moz-placeholder {
        color: transparent;
    }
    .bili-dm-vip {
        background: none !important;
        text-shadow: 1px 1px 2px #000000,0 0 1px #000000 !important;
    }
    .left-entry li, .mini-header__arrow {
        visibility:hidden;
    }
    a.entry-title, a.left-entry__title {
        visibility:visible;
    }
}

@-moz-document domain("t.bilibili.com") {
    .bili-dyn-version-control__btn {
        display: none !important;
    }
}
```

# 清理bilibili搜索页广告
```javascript
// ==UserScript==
// @name         Block AD
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @include      *.bilibili.*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=bilibili.com
// @grant        none
// ==/UserScript==

(function() {
    window.addEventListener('transitionend',function(){
        var a = document.querySelectorAll(".bili-video-card__info--ad");
        for(var i=0; i<a.length; i++) {a[i].parentElement.parentElement.parentElement.parentElement.parentElement.parentElement.parentElement.remove()};
    },false);
})();
```