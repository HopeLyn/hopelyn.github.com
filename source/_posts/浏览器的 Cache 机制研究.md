---
title: 浏览器的 Cache 机制研究
date: 2017-02-14 14:35:28
categories: 未完成
tags: 
---

## 测试过程
*   打开网页可以发现图都是 `from memory cache` 方式获取的，另外还有一些 `from disk cache` 的则是浏览器插件的 js 和 css 文件

![](media/14870541119124/14870545904964.jpg)

*   按照网上说的([StackOverflow: Using <meta> tags to turn off caching in all browsers]((http://stackoverflow.com/questions/1341089/using-meta-tags-to-turn-off-caching-in-all-browsers)))，添加了清除缓存语句，然而图片还是 `from memory cache`，说明图片的缓存并不受 meta 控制

    ```html
  <meta http-equiv="cache-control" content="max-age=0" />
  <meta http-equiv="cache-control" content="no-cache" />
  <meta http-equiv="expires" content="0" />
  <meta http-equiv="expires" content="Tue, 01 Jan 1980 1:00:00 GMT" />
  <meta http-equiv="pragma" content="no-cache" />
    ```
    
    ```html
    <meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />
    <meta http-equiv="Pragma" content="no-cache" />
    <meta http-equiv="Expires" content="0" />
    ```

*   在 Chrome 浏览器下，可以通过 `chrome://cache` 地址来查看当前 chrome 缓存的文件

![](media/14870541119124/14870587533341.jpg)

*   发现工程中的文件有时候是 `from disk cache`，有时候是 `from memory cache`

![](media/14870541119124/14870618446585.jpg)

*   加入了以下语句以后，清除缓存加刷新页面，ubt 文件加载了一次以后还是会显示 `from disk cache`，说明语句并没有起作用

![](media/14870541119124/14870623717107.jpg)

![](media/14870541119124/14870623524159.jpg)

*   **memory cache** vs **disk cache**: 按照 Reddit 上的回答[What is the difference between disk caching and memory caching?](https://www.reddit.com/r/explainlikeimfive/comments/3660ig/eli5what_is_the_difference_between_disk_caching/)，浏览器缓存一般存于 **disk cache**，而系统缓存一般存于 **memory cache**

![](media/14870541119124/14870635219273.jpg)


## 相关链接
*   [StackOverflow: How to control web page caching, across all browsers](http://stackoverflow.com/questions/49547/how-to-control-web-page-caching-across-all-browsers): 赞同最多的答案
*   [StackOverflow: Using <meta> tags to turn off caching in all browsers]((http://stackoverflow.com/questions/1341089/using-meta-tags-to-turn-off-caching-in-all-browsers))

