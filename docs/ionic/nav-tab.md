## 导航
这个没什么介绍的，[官网](https://ionicframework.com/docs/api/components/nav/Nav/) 也说的很少。平时也可以说用不上。

!> 使用时，必须设置根页面，将根页面的路由赋给“root”属性。

## 导航栏
Navbar充当导航工具栏，如果当前页面不是根页面，左边还带有后退按钮。点击后退按钮相当于 `this.navCtrl.pop();`

!> navbar是动态导航堆栈的一部分。如果需要静态工具栏，请使用ion-toolbar。

使用命令行创建的页面都会自动生成导航栏的代码，一般用法也就是那样，不过有时候你也会有其他需求：

* 导航栏隐藏返回按钮，自定义左右侧按钮

```html
<!-- one.html -->

<ion-header>
  <ion-navbar hideBackButton>
    <ion-buttons left>
      <button ion-button (click)="back()">
        <ion-icon class="customIcon" name="arrow-back"></ion-icon>
      </button>
    </ion-buttons>
    <ion-title>One</ion-title>
    <ion-buttons end>
      <button ion-button icon-only (click)="openModal()">
        <ion-icon name="options"></ion-icon>
      </button>
    </ion-buttons>
  </ion-navbar>
</ion-header>
```
* 改变导航栏返回按钮的点击事件

?> 这个需求在开发中也是的会经常用到的

```
<!-- three.html -->

<ion-header>
  <ion-navbar #navbar>
    <ion-title>three</ion-title>
  </ion-navbar>
</ion-header>

<!-- three.ts -->

import { ViewChild } from '@angular/core';

export class ThreePage {

  @ViewChild('navbar')
  navbar: any;

  ionViewDidLoad() {
    this.navbar.backButtonClick = (event: UIEvent) => {
      console.log('返回按钮点击', event);
      this.navCtrl.popToRoot();
    }
  }
}
```

## 标签
[ion-tab](https://ionicframework.com/docs/api/components/tabs/Tab/) 是 NavController 的声明性组件，也就是同 `ion-nav`一样，每一个 tab 都是一个 NavController。<br>
它与 Tabs 组件一起使用。

```
<ion-tabs>
  <ion-tab [root]="chatRoot" tabTitle="Chat" tabIcon="chat" [rootParams]="chatParams"></ion-tab>
</ion-tabs>
```

!> 有时您可能想要调用方法而不是导航到新页面。可以使用 `(ionSelect)` 事件，该事件在选择标签时发出。

```
<!-- tabs.html -->

<ion-tabs>
  <ion-tab (ionSelect)="chat()" tabTitle="Show Modal"></ion-tab>
</ion-tabs>

<!-- tabs.ts -->

export class Tabs {
  constructor(public modalCtrl: ModalController) {}

  chat() {
    let modal = this.modalCtrl.create(ChatPage);
    modal.present();
  }
}
```

`ion-tabs` 的`select`方法，选择跳转某个标签

```
<ion-tabs #myTabs>
  <ion-tab [root]="tab1Root" #tab0></ion-tab>
  <ion-tab [root]="tab2Root"></ion-tab>
  <ion-tab [root]="tab3Root"></ion-tab>
</ion-tabs>

export class TabsPage {
  @ViewChild('myTabs') tabRef: Tabs;
  @ViewChild('tab0') tab0: NavController;

  ionViewDidEnter() {
    this.tabRef.select(2);
  }

  switchTabs() {
    this.tab0.parent.select(2);
  }
}
```

`ion-tabs` 的 `(ionChange)` 事件，标签更改时发出的事件。