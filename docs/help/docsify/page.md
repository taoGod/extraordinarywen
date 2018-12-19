docsify 使用并扩展了Markdown语法，使文档更具可读性。<br>

## markdown
[markdown基本语法](https://www.jianshu.com/p/191d1e21f7ed)<br>
[Markdown 语法整理](https://www.jianshu.com/p/b03a8d7b1719)<br>

### 引用

```
> 引用金句
```

> 引用金句

## 重要内容提示

```
!> **Time** is money, my friend!
```

!> **Time** is money, my friend!

## 一般内容提示

```
?> **Time** is money, my friend!
```

?> **Time** is money, my friend!

## 链接

```
// 一般形式
[link](/demo/)

// 忽略链接，将不再编译该链接
[link](/demo/ ':ignore')
[link](/demo/ ':ignore title')

// 设置链接的目标属性
[link](/demo ':target=_blank')
[link](/demo2 ':target=_self')

// 禁用
[link](/demo ':disabled')

```

## 图片

```
![logo](https://docsify.js.org/_media/icon.svg ':size=50x100')
![logo](https://docsify.js.org/_media/icon.svg ':size=100')
![logo](https://docsify.js.org/_media/icon.svg ':size=10%')
```

## 设置标题ID

```
### 你好，世界！ :id=hello-world
```

## markdown in html

```
<details>
<summary>运动列表 (放开)</summary>

- 篮球
- 足球

</details>

<div style='color: red'>

- 篮球
- 足球

</div>

```

<details>
<summary>运动列表 (放开)</summary>

- 篮球
- 足球

</details>

<div style='color: red'>

- 篮球
- 足球

</div>
