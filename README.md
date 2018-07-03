# Vue-TcPlayer

简单封装了腾讯 TCPlayer Lite 的非官方 [Vue](https://github.com/vuejs/vue) 组件。
[官方文档](https://cloud.tencent.com/document/product/267/7479)

## 使用方法

1. 安装组件

```shell
npm install vue-tcplayer
```

2. 在页面文件中引入 TCPlayer 脚本

```html
<script src="//imgcache.qq.com/open/qcloud/video/vcplayer/TcPlayer-2.2.1.js" charset="utf-8"></script>
```

3. 将 Vue-TcPlayer 作为组件引入 Vue。简单示例如下：

```javascript
import TcPlayer from 'vue-tcplayer'

const app = new Vue({
  el: '#app',
  components: {
    TcPlayer
  }
})
```

## Props

* **width**: Number/String
* **height**: Number/String
* **listener**: Function
* **live**: Boolean
* **options**: Object

各个 prop 的说明详见官方文档的 [参数列表](https://cloud.tencent.com/document/product/267/7479#%E5%8F%82%E6%95%B0%E5%88%97%E8%A1%A8)。其中，`options` 为 `width`、`height`、`listener`、`live` 之外参数的集合。

## 方法

支持 [实例方法列表](https://cloud.tencent.com/document/product/267/7479#%E5%AE%9E%E4%BE%8B%E6%96%B9%E6%B3%95%E5%88%97%E8%A1%A8) 所列的方法。