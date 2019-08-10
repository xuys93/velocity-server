# velocity-server

## 功能

 - vm模板渲染
 - 静态资源服务
 - `.json`、`.json5`文件支持[json5](https://github.com/json5/json5)语法，响应内容为json格式

## 安装

0. 目录下运行`npm install`

0. 可编辑`config/local.json`，webapps配置项更改服务根目录


## 使用说明

如果模板文件同目录下有同名的js文件，则作为模板的模拟数据，例如：

index.vm

```html
<h1>${title}</h1>
<ul>
    #foreach($item in $list)
    <li>$item</li>
    #end
</ul>
<p>Today is $now()</p>
```

index.js

```js
module.exports = {
    "title": "hello title",
    "list": [
        "one",
        "two",
        "three"
    ],
    "now": function() {
        return (new Date).getDay();
    }
}
```

## 运行

    npm run server    

## 测试

    npm run test
