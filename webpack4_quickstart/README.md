---
webpack4 quick start
---

## Environment

OS: `window 10`

powershell: `5.1`

npm: `6.6.0`

node: `v10.13.0`

webpack: `4.29.0`

## Quick start

shift+右击, 启动 `PowerShell`, 创建一个目录并进入

```
mkdir webpack4
```

```
cd webpack4
```

初始化 `package.json`

```
npm init -y
```

安装 `webpack4` 和 `webpack-cli`

```
npm i webpack webpack-cli -D
```

添加构建指令 `package.json`

```json
"scripts": {
  "build": "webpack"
}
```

试着构建

```
npm run build
```

非常抱歉，现在可以看到一个`warn`和 一个`error`

`warn` The 'mode' option has not been set

`error` ERROR in Entry module not found: Error: Can't resolve './src' in 'xxx'

让我们解决它

第一个`warn`

修改构建指令，其中 `development` 代表开发模式，`production` 代表生产模式。参考[构建模式](https://webpack.js.org/concepts/mode/)

```json
"scripts": {
  "dev": "webpack --mode development",
  "build": "webpack --mode production"
}
```

第二个 `error`

`webpack4.x`  增加了默认的入口和出口，`./src/index.js` 为入口默认文件，`./dist/main.js` 为出口默认文件。`error` 异常原因是  `webpack-cli` 没有找到入口默认文件，现在让我们创建一个入口文件 `./src/index.js`

```javascript
console.log(`hello webpack4`);
```

再次构建（这里使用开发模式 `dev` ）

```
npm run dev
```

可以看到生成了出口文件 `./dist/main.js` 

大功告成



## 参考

[webpack 文档](https://webpack.js.org/concepts/)