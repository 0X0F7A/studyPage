## 更整洁的bilibili
```css
/* ==UserStyle==
@name           2023/5/17 09:53:09
@namespace      github.com/openstyles/stylus
@version        1.0.0
@description    A new userstyle
@author         Me
==/UserStyle== */

@-moz-document domain("bilibili.com") {
    .trending, .nav-user-center .t .num, .bili-header .red-num--message {
        display:none !important;
    }
}

@-moz-document domain("www.bilibili.com") {
    .relative-container, .recommended-swipe-core, .bili-grid, .eva-banner, .vip-wrap, .ad-report:not(:empty), 
    .video-card-ad-small, .recommended-swipe, .primary-btn.go-back, .link-item.link-item__right, .other-link, 
    .footer-icons, .pop-live-small-mode, .red-num--dyn, .pop-live-small-mode, #bili-header-banner-img, 
    .red-num--dynamic {
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
    .trending, .adaptive-scroll, .nav-user-center .t .num, .topic-panel, .bili-dyn-publishing, 
    .bili-dyn-publishing .topic-panel, .bili-dyn-ads {
        display:none;
    }
    .nav-search-keyword::-moz-placeholder {
        color:#1f2121;
    }
}

@-moz-document domain("space.bilibili.com") {
    .blankforscctest, .trending, .trending-item, .bilibili-player-score, .nav-search-keyword::-moz-placeholder,
    .dyn-topic-panel, .nav-user-center .t .num, .bili-header .red-num--message, 
    .mini-header .left-entry .v-popover-wrap {
        display: none;
    }
    .nav-search-input::placeholder {
        color:#1f2121;
    }
}
```

## 清理bilibili搜索页广告
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
## 自定义的百度界面
```css
/* ==UserStyle==
@name           2023/2/17 17:07:33
@namespace      github.com/openstyles/stylus
@version        1.0.0
@description    A new userstyle
@author         Me
==/UserStyle== */


@-moz-document domain("baidu.com"), domain("baidu.com/s") {
    .s_btn, .s_btn:hover {
        background-color: #42c3d4 !important;
        color: #161d4b !important;
    }
    #s_lg_img {
        filter: invert(100%) grayscale(100%);
    }
    #head_wrapper #kw:focus {
        border-color: #42c3d4 !important;
    }
    #head_wrapper .soutu-btn:hover {
        filter: hue-rotate(-50deg) brightness(160%);
    }
    #result_logo {
        filter: invert(100%) grayscale(100%);
    }
    ::after {
        background-color: #42c3d4 !important;
    }
    .wrapper_new #form .bdsug-new, .wrapper_new .iptfocus.s_ipt_wr, .wrapper_new .s_ipt_wr.new-ipt-focus {
        border-color: #42c3d4 !important;
    }
    #content_left a {
        color: #9fe5f5 !important;
    }
    #content_left a:visited {
        color: #b78edd !important;
    }
    #content_left a:hover {
        color: #d0f3fb !important;
    }
    #content_left a:hover:visited {
        color: #dab9f9 !important;
    }
    #content_left a:hover:visited em {
        color: #ff9595 !important;
    }
    .hint_right_middle {
        border-bottom-color: #070809 !important;
    }
    #content_right .new-pmd .c-img-border {
        border-color: #070809 !important;
    }
    #content_right .opr-recommends-img-border-span {
        border-color: #070809 !important;
    }
    .s-top-left,.s-top-right, #bottom_layer, #s_lm_wrap, .FYB_RD, #s_wrap, .s-hotsearch-wrapper, #s_side_wrapper {
        display: none;
    }
    #head_wrapper {
        height: 60%;
    }
    #head_wrapper.s-ps-islite .s-p-top {
        bottom: 60px;
    }
    #head_wrapper .s-p-top{
        top:220px;
    }
    .c-result-content {
        filter: contrast(0%) brightness(6%);
        color: #070809 !important;
    }
    .container_l.sam_newgrid #content_right {
        width:1px;
        height:1px;
        left: 10000px;
        position: relative;
    }
    #container.sam_newgrid {
        width:1px;
    }
    .a {
        color: #070809 !important;
    }
    #content_right {
        filter: contrast(0%) brightness(6%);
        visibility: hidden;
    }
}
```