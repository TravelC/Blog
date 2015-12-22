# TCRoundedCorner
Scroll down for english version.

This is a category of UIView which provided the ability of add specified corner(s) to a view with a optional border.
这是UIView的一个分类，用来指定view的某（几）个角位圆角，同时有可选的的边框，你也可以只加边框而不设置圆角。

![](https://github.com/TravelC/TCRoundedCorner/blob/master/demoOfTCRoundedCorner.gif)

安装
==========================

#### Cocoapod :-

`pod 'TCRoundedCorner', '~> 1.0.0'`

#### 源代码:-
把文件夹 TCRoundedCorner 里面的文件加到你的项目里面.

## 如何使用

1.仅设置 myView 圆角:

```
[self.myView roundedCorner:type radius:20.0];
```

2.设置圆角和边框:

```
[self.myView roundedCorner:type radius:20.0 borderColor:borderColor borderWidth:5.0];
```

3.只设置边框:

```
[self.myView addBorderWithColor:borderColor borderWidth:5.0];
```
4.移除边框:

```
[self removeBorder];
```
 

开原许可
---
Distributed under the MIT License.

作者
---
If you wish to contact me, email at: chuchuanming@gmail.com

博客
---
[http://travelchu.com](http://travelchu.com)

#  ----------


# English Verwion

This is a category of UIView which provided the ability of add specified corner(s) to a view with a optional border.

![](https://github.com/TravelC/TCRoundedCorner/blob/master/demoOfTCRoundedCorner.gif)

Installation
==========================

#### Cocoapod Method:-

`pod 'TCRoundedCorner', '~> 1.0.0'`

#### Source Code Method:-
Add files in folder TCRoundedCorner to your project.

## How To Get Started

1.Only round myView's corners:

```
[self.myView roundedCorner:type radius:20.0];
```

2.Round corners and add a border together:

```
[self.myView roundedCorner:type radius:20.0 borderColor:borderColor borderWidth:5.0];
```

3.Add border only:

```
[self.myView addBorderWithColor:borderColor borderWidth:5.0];
```
4.Remove border:

```
[self removeBorder];
```
 

LICENSE
---
Distributed under the MIT License.

Author
---
If you wish to contact me, email at: chuchuanming@gmail.com

Blog
---
[http://travelchu.com](http://travelchu.com)