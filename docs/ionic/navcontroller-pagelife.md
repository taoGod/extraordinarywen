## 导航控制器介绍
在 one.ts 中有过 `constructor(public navCtrl: NavController, public navParams: NavParams) {}` ，`NavController` 是什么呢？<br>
> `NavController` 是导航栏控制器组件的基类。[Nav](https://ionicframework.com/docs/api/components/nav/Nav/) 和 [Tab](https://ionicframework.com/docs/api/components/tabs/Tab/) 就是这样的组件。
导航栏控制器用来导航页面。它以栈的形式管理一个数组，该数组可以推送和弹出页面或插入和删除指定页面。当前页面也就是最新入栈的页面位于位于栈顶，导航控制器最先弹出的页面就是当前页面。

!> 官方用的view，效果就是一个页面，所以我大概差不多说的页面和视图的都是view。总之词汇那种东西吧，希望别计较那么多，代码和效果才是硬道理。当然我也希望能尽量用词恰当，希望多指正。

## 推送视图
使用`pop()`。

```ts
<!-- home.ts -->

constructor(public navCtrl: NavController) {}

go2OnePage() {
  this.navCtrl.push('OnePage');
}
```

也可以穿参，可以是一个值，也可以是一个json对象。参数怎么获取可参考 [NavParams](https://ionicframework.com/docs/api/navigation/NavParams/)

```
<!-- home.ts -->

constructor(public navCtrl: NavController) {}

go2OnePage() {
  this.navCtrl.push('TwoPage', { id: 007 });
}

<!-- two.ts -->

constructor(public navCtrl: NavController, public navParams: NavParams) {
  console.log(this.navParams.data);
}
```

## 移除视图
* 移除当前视图

```
popView(){
  this.navCtrl.pop();
}
```

* 只留根视图

```
popToRootView(){
  this.navCtrl.popToRoot();
}
```

## 生命周期事件

> ionic 的生命周期事件在**导航**的各个阶段被触发。

|事件                     | 返回       | 描述       |
| :---------------------: | :-------: | :-------------: |
| **`ionViewDidLoad`**    | 无        | 页面加载后运行。     |
| **`ionViewWillEnter`**  | 无        | 页面即将进入并成为活动页面时运行。     |
| **`ionViewDidEnter`**   | 无        | 页面完全进入后运行，现在是活动页面。     |
| **`ionViewWillLeave`**  | 无        | 页面即将离开且不再是活动页面时运行。     |
| **`ionViewDidLeave`**   | 无        | 页面完成离开后运行，不再是活动页面。     |
| **`ionViewWillUnload`** | 无        | 在页面即将被销毁并删除其元素时运行。     |
| **`ionViewCanEnter`**   | `boolean` | 在视图可以进入之前运行。进入之前检查权限 |
| **`ionViewCanLeave`**   | `boolean` | 在视图可以离开之前运行。离开之前检查权限 |

