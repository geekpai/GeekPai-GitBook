##ReactNative入门基础
###安装
1. VSCode ReactNativa插件(终端快捷键：ctrl + ~)
2. ext install vscode-react-native(F1/ctrl+P)
3. 安装Android Studio
4. 安装NPM
>如果安装不成功或者很慢，是因为react-native命令是从npm官网源安装，我们可以改用淘宝镜像源来安装
```
 $ npm config set registry https://registry.npm.taobao.org
 $ npm config set disturl https://npm.taobao.org/dist
```
>npm自升级：npm -g install npm@3.7.0
>进入刚刚目录下的react-native目录下的react-native-cli目录，输入npm install -g

###配置步骤
Android环境要求如下，请确保你的环境已经达到如下要求:
1. Android Sdk版本23(在build.gradle中的compileSdkVersion)
2. SDK build tools version 23.0.1(build.gradle中buildToolsVersion)
3. Android Support Repository>=17
4. Andoid NDK需要安装以及配置

###克隆运行代码
1、`git clone https://github.com/facebook/react-native.git`
2、添加node_modules模块(其中包含了react-native核心库) ：`npm install`
3、运行如下命令开始编译安装我们的官方实例
```
gradle :Examples:UIExplorer:android:app:installDebug  或
./gradlew :Examples:UIExplorer:android:app:installDebug
```
4、接下来就是最关键的一步啦~执行如下命令进行打包启动服务.
`./packager/packager.sh`

###更新 React Native 项目依赖包版本
>在升级之前，我们可以运行 npm infi react-native查看react-native的版本信息：
```
  $ npm update -g react-native-cli  // 更新本地 react-native-cli的版本
  $ npm install --save react-native@0.20 // @后面跟需要升级的版本号
  $ react-native upgrade
```
>降级 React Native 项目依赖包版本 (与更新一样)
```
  $ npm install --save react-native@0.18 // @后面跟需要升级的版本号
  $ react-native upgrade
```

###Init项目慢
>直接使用了命令去替换了NPM
>`$ npm install -g cnpm --registry=https://registry.npm.taobao.org`
>这样一来，就会快很多了，实测，大概3分钟。


###React Native移植原生Android项目
1. 首先我们有一个采用Gradle构建的Android应用项目，这个大家直接采用Android Studio进行创建一个项目即可。我这边新建一个目录TestInte，然后采用Android Studio创建一个android项目在该文件夹下面。
2. 电脑必须安装Node.js，具体安装使用方法(点击进入)
3. Android项目相关配置
>在我们Android项目的build.gradle中添加React Native依赖，然后同步，具体代码如下:
1. `compile 'com.facebook.react:react-native:+'`
2. 紧接着我们需要在项目AndroidManifest.xml中加入网络访问权限
   `<uses-permission android:name="android.permission.INTERNET" />`
>该仅仅用于开发阶段从开发服务器加载最细的JavaScript代码，在正式发布版本中，如果有需要可以把该网络权限删掉。
3. 添加原生代码
>在Android项目的MainActivity中，我们需要配置相关代码来进行启动运行React Native库。我这边直接采用>=0.18版本的写法了，到此为止我们的Android项目Activity和配置文件以及完成了最基本的配置方法了。
4. 添加js
>下面我们采用命令行，首先切换到项目的根目录上面(我的例子是切换到TestIntegrating目录下)
>*命令行运行npm init 运行截图如下:该命令会创建一个package.json文件，并且提示我们输入一些信息，默认不输入即可，不过name必须要为全英文小写哦，具体结果执行结果如下:
* 接下来我们在在scripts标签那边添加如下代码:
  `"start": "node node_modules/react-native/local-cli/cli.js start"`
  以及添加react依赖`:"react": "15.0.2"`和react-native依赖:`"react-native": "^0.26.3",`
>然后在项目根目录下面执行npm install安装依赖模块