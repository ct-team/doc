# bower 用法

## 安装bower

```javascript
npm install -g bower
```

## 注册模块

```javascript
bower register git:github.com/ct-team/store.js.git //模块git地址 
```

## 加载模块

```javascript
bower install jquery
```

## 卸载模块

```javascript
bower uninstall jquery
```

## 自定义包的安装目录

进入项目目录下，建立一个文件.bowerrc 内容：
```javascript
{
  "directory" : "js/lib" //自定义路径
}
```
