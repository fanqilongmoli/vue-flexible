# vue-flexible
## vue-cli3.0结合lib-flexible、px2rem实现移动端适配，完美解决第三方ui库样式变小问题

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## ----------------------------
### 项目中安装lib-flexible

```
npm install lib-flexible --save
```
### 在项目的入口js文件中引入lib-flexible
```
import 'lib-flexible'
```
lib-flexible会自动在html的header中添加一个meta name="viewport"的标签,
同时会自动设置html的font-size为屏幕宽度除以10，也就是1rem等于html根节点的
font-size。<br>
假如设计稿的宽度是750px，此时1rem应该等于75px。假如量的某个元素的宽度是150px，
那么在css里面吨关于的这个元素的宽度就是 width:2rem; <br>
注意：<br>
    1.检查一些html的head中，如果有meta name="viewport"标签，需要将它注释掉，
因为如果有这个标签的话，lib-flexible就会默认使用这个标签。
而我们需要使用lib-flexible自己生成的标签。<br>
    2.因为html的font-size是根据屏幕宽度除以10计算出来的，所以我们需要设置页面的最大宽度是10rem。<br>
    3.如果个别地方不想转化px。可以简单的使用大写的 PX 或 Px 
### 使用 postcss-px2rem-exclude
#### 正确的配置位置是项目根目录下的postcss.config.js文件，如果你的项目没有生成这个独立文件，就需要在你的package.js里设置
```
postcss.config.js

module.exports = {
  plugins: {
    autoprefixer: {},
    "postcss-px2rem-exclude": {
      remUnit: 75,
      exclude: /node_modules|folder_name/i
    }
  }
};


package.json

"postcss": {
    "plugins": {
      "autoprefixer": {},
      "postcss-px2rem-exclude":{
          "remUnit": 75,
          "exclude":"/node_modules|floder_name/i"
      }
    }
  },

```

## 参考
[使用Flexible实现手淘H5页面的终端适配](https://www.w3cplus.com/mobile/lib-flexible-for-html5-layout.html)
[vue移动端屏幕适配](https://blog.csdn.net/qq345930282/article/details/82219686)