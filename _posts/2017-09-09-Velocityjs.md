---
layout: post
title: "Velocity.js动画"
author: "ryy"
---

概述


    Velocity 是一个简单易用、高性能、功能丰富的轻量级JS动画库。它能和 jQuery 完美协作，并和$.animate()有相同的 API， 但它不依赖 jQuery，可单独使用。
    
    Velocity 不仅包含了 $.animate() 的全部功能， 还拥有：颜色动画、转换动画(transforms)、循环、 缓动、SVG 动画、和 滚动动画 等特色功能。
    
    它比 $.animate() 更快更流畅，性能甚至高于 CSS3 animation， 是 jQuery 和 CSS3 transition 的最佳组合，它支持所有现代浏览器，最低可兼容到 IE8 和 Android 2.3。
    
    
官网
 http://velocityjs.org/
 
实例

    HTML 
    <body>
        <!-- dom -->
        <div class="element"></div>
    
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/velocity/1.5.0/velocity.min.js"></script>
    </body>
    JavaScript 
    // 标准写法
    // (为了简洁，后面的示例代码中 将直接使用 $element 来代替 jQuery 选择器)
    $(".element").velocity({
        left: "200px"
    }, {
        duration: 450,
        delay: 1000
    });
    
    // $.animate() 的写法，效果同上
    $(".element").delay(1000).velocity({left: "200px"}, 450);	
