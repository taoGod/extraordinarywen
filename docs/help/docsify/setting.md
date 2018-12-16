## index.html
这个文档非常重要，整个网站的相关配置都跟它有莫大关联。

### Loading dialog
进入网站或刷新页面时的loading
```
<div id="app">Please wait...</div>

// 上面的 id 可以更改，如果更改了，则需要做以下配置
<div data-app id="main">Please wait...</div>
<script>
  window.$docsify = {
    el: '#main'
  }
</script>
```

## sideBar




