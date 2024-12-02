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
    .red-num--dynamic, #reco_list, #slide_ad {
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
    /* for fucking newer version*/
    .floor-single-card, .bili-live-card, .desktop-download-tip {
        display: none;
    }
    .recommended-container_floor-aside .container > :nth-of-type(n+8) {  /* this fix the gap of the large banner */
        margin-top: 0px !important;
    }
    .feed-card .bili-video-card.is-rcmd {  /* this part fix the ever scrolling */
        display: block;
    }
    .bili-video-card {
        display:none;
    } /* till here */
}

@-moz-document domain("t.bilibili.com") {
    .bili-dyn-version-control__btn {
        display: none !important;
    }
    .trending, .adaptive-scroll, .nav-user-center .t .num, .topic-panel, .bili-dyn-publishing, 
    .bili-dyn-publishing .topic-panel, .bili-dyn-ads, .bili-dyn-version-control__reminding {
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

## 新版bilibili禁止无限下拉&清除广告及创意广告
```javascript
// ==UserScript==
// @name         Block AD
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @match        www.bilibili.com
// @icon         https://www.google.com/s2/favicons?sz=64&domain=bilibili.com
// @grant        none
// ==/UserScript==

(function() {
    window.addEventListener('transitionend',function(){
        var a = document.querySelectorAll(".bili-video-card__info--ad");
        for(var i=0; i<a.length; i++) {a[i].parentElement.parentElement.parentElement.parentElement.parentElement.parentElement.remove()};
        a = document.querySelectorAll(".bili-video-card__info--creative-ad");
        for(i=0; i<a.length; i++) {a[i].parentElement.parentElement.parentElement.parentElement.parentElement.parentElement.remove()};
        /* a = document.querySelector(".container.is-version8").childNodes;
        for(i=0; i<a.length; i++) {
            if(a[i].nodeType == 1) {
                if(a[i].attributes.class.nodeValue == "feed-card");
                else {
                    a[i].remove();
                }
            }
        } */
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

## 反反adblocker弹窗脚本

修改自 [https://github.com/TheRealJoelmatic/RemoveAdblockThing](https://github.com/TheRealJoelmatic/RemoveAdblockThing)

```javascript
// ==UserScript==
// @name         Remove Adblock Thing(edited)
// @namespace    http://tampermonkey.net/
// @version      5.6
// @description  Removes Adblock Thing
// @author       JoelMatic
// @match        https://www.youtube.com/*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=youtube.com
// @downloadURL  https://github.com/TheRealJoelmatic/RemoveAdblockThing/raw/main/Youtube-Ad-blocker-Reminder-Remover.user.js
// @grant        none
// ==/UserScript==

(function()
 {
    // Enable The Popup remover (pointless if you have the Undetected Adblocker)
    const removePopup = true;
    // Enable debug messages into the console
    const debugMessages = true;

    // Set everything up here
    log("Script started");

    if (removePopup) popupRemover();

    // Remove Them pesski popups
    function popupRemover() {

        setInterval(() => {
            // how to see what to change, watch the element handler_arg_b for change in attribute, then see the stack 
            const modalOverlay = document.querySelector("tp-yt-iron-overlay-backdrop");
            const popup = document.querySelector(".style-scope ytd-enforcement-message-view-model");
            const handler_arg_b = popup.parentElement;
            // handleClosePopupAction_
            const popupButton = document.getElementById("dismiss-button");

            var video = document.querySelector('video');

            const bodyStyle = document.body.style;
            bodyStyle.setProperty('overflow-y', 'auto', 'important');

            if (modalOverlay) {
                modalOverlay.removeAttribute("opened");
                // modalOverlay.remove();
            }

            if (popup && popupButton) {
                log("Popup detected, removing...");

                handler_arg_b.close();
                popup.remove();
                video.play();

                /*setTimeout(() => {
                    // video.play();
                }, 500);*/

                log("Popup removed");
            }
            // Check if the video is paused after removing the popup
            // if (!video.paused) return;
            // UnPause The Video
            // video.play();

        }, 1000);
    }

})();

```

```css
@-moz-document domain("www.youtube.com") {
    /*, ytd-popup-container*/
    .masthead-ad, ytd-ad-slot-renderer, ytd-reel-shelf-renderer, ytd-enforcement-message-view-model, tp-yt-iron-overlay-backdrop{
        display: none;
    }
}
```