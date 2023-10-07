// ==UserScript==
// @name         Alan Chen03 - Google News Don't Jump
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @match        https://news.google.com/*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=google.com
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    console.log('extension is running!')

    //监听a链接的点击
    document.body.addEventListener("click",function (event) {
        var target = event.target || event.srcElement;      // 兼容处理
        if (target.nodeName.toLocaleLowerCase() === "a") {    // 判断是否匹配目标元素
            if(!target.getAttribute("href").startsWith('./article')){
                return;
            }
            if (event.preventDefault) {     // 对捕获到的 a 标签进行处理
                event.preventDefault();
            } else {
                event.returnValue = false;
            }
            choosePush(target); // 处理完 a 标签的内容，重新触发跳转，根据原来 a 标签页 target 来判断是否需要新窗口打开
        }
    })

    //判断是否需要新窗口打开
    function choosePush(el) {
        const target = el.getAttribute("target");
        const href = el.getAttribute("href");
        console.log(href)
        el.setAttribute('target','_self')
        window.location.href = 'https://news.google.com' + href.substr(1);
    }


})();
