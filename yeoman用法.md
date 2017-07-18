# yeoman用法

## 安装Yeoman

安装 Yeoman 的命令行工具   

```javascript
npm install -g yo
```

## 使用Yeoman

选择Yeoman模板 初始化项目   

```javascript
yo you-name
```

## 自定义模板方法

yo和专用于开发 Yeoman 生成器的工具 generator-generator

```javascript
  npm install -g yo generator-generator
```
使用它们创建一个生成器的初始化目录

```javascript
  yo generator
```
执行上述命令后，Yeoman 会在终端向开发者提出一个问题，是一个交互式的配置过程。

### 配置内容

```javascript
  'use strict';
var yeoman = require('yeoman-generator');
var chalk = require('chalk');
var yosay = require('yosay');
module.exports = yeoman.Base.extend({
// 1. 接收参数
prompting: function (){
var prompts = [{
type: 'input',
name: 'appName',
message: 'Give your app a name: ',
default: 'yoAppName'
}];
return this.prompt(prompts).then(function (props){
// 1.1 将参数挂载在 this 下
this.props = props;
}.bind(this));
},
// 2. 渲染模版
writing: function (){
// ...
},
// 3. 安装依赖
install: function (){
this.npmInstall();
}
});
```
### 测试

这里是收尾工作，使用 npm 的工具将生成器安装到全局，在我们创建的生成器的根目录下：

```javascript
  npm link
```
新建文件夹进行测试

```javascript
  yo you-name
```

### 发布

npm 发布
git 上传

