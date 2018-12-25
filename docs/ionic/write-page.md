?> 个人感觉还是先看一下 angular、css 或 [官方demo](https://github.com/ionic-team/ionic-preview-app) 比较好。下面会列举一些常用的例子，另外我觉得。如果不需要组件的特有功能，则不推荐使用官方组件，推荐使用比较简单的 H5元素，写一下样式即可。

## 页面元素的显示与隐藏

> `ng-if` 指令在表达式为 false 时移除 HTML 元素，在表达式为 true时会添加移除元素，并显示。ng-if 指令不同于 `ng-hide`， `ng-hide` 是隐藏元素。

```
<!-- xxx.html -->

<div *ngIf="person.check">{{ person.name }}</div>

<!-- xxx.ts -->

person = {
  name: 'wer',
  check: true
};
```

## 页面元素的循环

> `ng-for`

```html
<ion-list>
  <ion-item *ngFor="let news of newsArr; let i = index">
    <h1>{{i + '、' + news.title}}</h1>
    <ion-label>{{news.content}}</ion-label>
  </ion-item>
</ion-list>
```

## 页面元素的样式

> `ng-style`

```html
<div [ngStyle]="{'display':item.checked===true ? 'block' : 'none' }">
  <img class="icon" src="{{item.icon}}" />
  <div class="text">{{item.text}}</div>
</div>
```

## 元素id

angular
