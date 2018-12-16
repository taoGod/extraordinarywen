这个后边慢慢补充吧，可以进该网站的 [代码仓库](https://github.com/taoGod/extraordinarywen)，瞅一眼 `index.html`。<br>
也可以看一下 [官网](https://docsify.js.org/#/configuration)。

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>非凡的阿文</title>
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
    <meta name="description" content="Description" />
    <meta
      name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"
    />
    <link rel="stylesheet" href="//unpkg.com/docsify/lib/themes/vue.css" />
    <link rel="stylesheet" href="//unpkg.com/vuep/dist/vuep.css" />
    <!-- <link rel="stylesheet" href="//unpkg.com/docsify/themes/dark.css"> -->

    <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.css">
    <style>
      section.cover .cover-main > p a {
        background-color: var(--theme-color, #42b983);
        color: #fff !important;
      }

      .markdown-section pre {
        background-color: #e8e8e8;
      }
      .markdown-section pre > code {
        background-color: #e8e8e8;
      }
      pre:after {
        color: #797676;
      }
    </style>
  </head>

  <body>
    <div id="app">加载中...</div>
    <script>
      window.$docsify = {
        name: '阿文',
        repo: 'https://github.com/taoGod/extraordinarywen', // 右上角小部件
        loadSidebar: true, //侧边栏，默认_sidebar.md，可自己指定，如：loadSidebar:'_side.md'
        alias: {
          // '/.*/_sidebar.md': '/_sidebar.md',
          '/.*/_navbar.md': '/_navbar.md'
        },
        autoHeader: false,
        loadNavbar: true, // 顶部路由 默认_navbar.md
        coverpage: true, // 激活封面功能-_coverpage.md，可配置多个
        onlyCover: false, // 主页仅加载封面，不能滚动到其他页
        subMaxLevel: 3, // 侧边栏层级
        auto2top: true, // 路线更改时滚动到屏幕顶部
        homepage: 'README.md', // 主页，默认是README.md，也可自己指定
        mergeNavbar: true, // Navbar将在较小的屏幕上与侧边栏合并
        formatUpdated: '{MM}/{DD} {HH}:{mm}',
        notFoundPage: '_404.md', //默认_404.md  可根据层级指定 notFoundPage:{'/':'_404.md','/app':'app/_404.md'}
        search: {
          placeholder: 'Search',
          noData: '暂无数据'
        },
        pagination: {
          previousText: '上一页',
          nextText: '下一页'
        },
        markdown: {
          renderer: {
            code: function(code, lang) {
              if (lang === "mermaid") {
                return (
                  '<div class="mermaid">' + mermaid.render('mermaid-svg-' + num++, code) + "</div>"
                );
              }
              return this.origin.code.apply(this, arguments);
            }
          }
        },
        executeScript: true,
        themeColor: '#3F51B5'
        // plugins: [
        //   function(hook) {
        //     var footer = [
        //       '<hr/>',
        //       '<footer style="position: fixed;bottom: 0;background: #ccc;width: 100%;height: 40px;line-height: 40px;text-align: center;">',
        //       '<span>&copy;2018.</span>',
        //       '<span> <a href="https://docsify.js.org/" target="_blank">docsify官网</a>.</span>',
        //       '</footer>'
        //     ].join('');

        //     hook.afterEach(function(html) {
        //       return html + footer;
        //     });
        //   }
        // ]
      };
    </script>
    <script src="//unpkg.com/docsify/lib/docsify.min.js"></script>
    <script src="//unpkg.com/docsify/lib/plugins/search.min.js"></script>
    <script src="//unpkg.com/docsify/lib/plugins/emoji.min.js"></script>
    <script src="//unpkg.com/docsify/lib/plugins/external-script.min.js"></script>
    <script src="//unpkg.com/docsify/lib/plugins/zoom-image.min.js"></script>
    <script src="//unpkg.com/docsify-copy-code"></script>
    <script src="//unpkg.com/vue/dist/vue.min.js"></script>
    <script src="//unpkg.com/vuep/dist/vuep.min.js"></script>

    <script src="//unpkg.com/docsify-pagination/dist/docsify-pagination.min.js"></script>
    <script src="//unpkg.com/prismjs/components/prism-bash.min.js"></script>
    <script src="//unpkg.com/prismjs/components/prism-php.min.js"></script>
    <script src="//cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
  </body>
</html>

```
