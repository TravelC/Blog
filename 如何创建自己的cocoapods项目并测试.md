##如何创建自己的Cocoapods项目并测试
# 
最近做了一个支持Cocoapods的开源项目[TCTitleLoading](https://github.com/TravelC/TCTitleLoading),总结了一下相关步骤。

###1. 创建项目并提交到Github

创建你的项目并提交到github，记下代码地址备用，如：https://github.com/TravelC/TCTitleLoading.git

###2. 创建Cocoapods使用的分支
创建一个供Cocoapods使用的分支，建议以版本号命名，如‘0.0.1’

###3. 创建podspec文件并编辑

打开终端，cd到项目目录，用‘pod spec create’命令创建podspec文件：

```
pod spec create test
```
其中test是podspec文件的名称，可以按自己需要修改。

文件创建之后就可以用自己喜欢的文本编辑器进行编辑了，里面有详细的注释，按需要填写即可。需要注意的是最终的文件是不能包含注释的，所以要把所有的注释都删掉。

###4. 验证podspec文件
打开终端，cd到podspec文件所在的目录，执行 ‘pod spec lint ’命令进行验证：

```
pod spec lint test.podspec
```

通过之后会显示 
```
xxx passed validation.
```
字样，如果有问题，会打印相应问题，修正后再次验证即可。如果想忽略警告，可增加--allow-warnings参数，如：

```
pod spec lint test.podspec --allow-warnings
```

###5. 测试
验证通过之后就可以在本地对项目进行测试了，新建一个测试项目，创建并初始化Podfile. Podfile内对要测试的pod填写格式如下：

```
pod "TCTitleLoading", :path => '../../TCTitleLoading'
```
其中path =>跟着的是podspec文件指定的代码所在的目录。

终端执行 ‘pod install’并做相关测试。

###6. 提交给Cocoapods公共库（Trunk）以便别人使用

测试通过后就可以提交到Cocoapods公共库（Trunk）以便别人使用啦。如果你还没有注册过，首先要执行注册命令：

```
pod trunk register 邮箱 '名字' --description='描述'
```

关于描述，由于注册不需要密码，是和电脑相关的，建议填写自己的电脑信息，如：‘Persional MacBook Pro’

注册之后先执行

```
pod lib lint

```
验证，当然也可以增加--allow-warnings参数以忽略警告：

```
pod lib lint --allow-warnings
```

验证通过后执行

```
pod trunk push TCTitleLoading.podspec --allow-warnings
```
当然--allow-warnings参数是可选的。

一切正常的的话你的项目就发布到Cocoapods啦。




