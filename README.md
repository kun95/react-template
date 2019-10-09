1.删除掉由create-react-app默认生成的js css等

2.创建文件夹
    - api 访问api接口
    - assets 资源
    - components UI组件
    - containers 容器组件 跟redux相关
    - redux redux相关
    - utils 工具类

3.设置 `index.html` 的 `meta` 信息
```<meta  name="viewport"  content="width=device-width,  initial-scale=1,  maximum-scale=1,  minimum-scale=1,  user-scalable=no"  />```

4.解决 点击延迟的问题 在 `index.html` 中
```
<script>
        if ('addEventListener' in document) {
            document.addEventListener('DOMContentLoaded', function () {
                FastClick.attach(document.body);
            }, false);
        }
        if (!window.Promise) {
            document.writeln('<script src="https://as.alipayobjects.com/g/component/es6-promise/3.2.2/es6-promise.min.js" ' + '>' + '<' + '/' + 'script>');
        }
</script>
```
5.按需加载
`npm install --save-dev babel-plugin-import react-app-rewired`

6.自定义配置 `config-overrides.js`
```javascript 1.8
const  {injectBabelPlugin}  =  require('react-app-rewired');
module.exports  =  function  override(config,  env)  {
config  =  injectBabelPlugin(['import',  {libraryName:  'antd-mobile',  style:  'css'}], config);
return  config;
}
```

7.修改 `package.json`
```javascript 1.8
  "scripts":  {
    "start":  "react-app-rewired  start",
    "build":  "react-app-rewired  build",
    "test":  "react-app-rewired  test  --env=jsdom",
    "eject":  "react-scripts  eject"
  },
```

