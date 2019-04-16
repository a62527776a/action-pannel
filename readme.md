# Vue ActionPannel

##### ❤❤❤❤ a beautiful Action Pannel ❤❤❤❤

<p align="center">
  <a href="https://www.npmjs.com/package/vue-action-pannel">
		<img src="https://img.shields.io/npm/v/vue-action-pannel.svg" alt="Version">
	</a>
	<!-- <img src="https://img.shields.io/badge/min+gzip-5.8_kB-blue.svg" alt="5.8 kB min+gzip"> -->
  <a href="https://github.com/a62527776a/vue-action-pannel/blob/master/LICENSE"><img
            src="https://img.shields.io/badge/license-MIT-brightgreen.svg" alt="License"></a>
  <br>
</p>

**[live demo](https://dscsdoj.top/public/vue-action-pannel/index.html)**


## Installation and use

```
$ yarn add vue-action-pannel
or
$ npm install vue-action-pannel --save
```

```
import App from './App.vue'
import ActionPannel from 'vue-action-pannel'
import Vue from 'vue'

Vue.use(ActionPannel)

new Vue({
  render: h => h(App)
}).$mount('#app')

```

```
data () {
  return {
    actions: [{
      icon: 'icon-article',
      text: '分享'
    }, {
      icon: 'icon-xiazai46',
      text: '客服'
    }, {
      icon: 'icon-yidong',
      text: '移动'
    }]
  }
}

methods: {
  openPannel: function () {
    let actionPannel = this.$createActionPannel({ // 函数式调用
      $props: {
        actions: this.actions // 传入列表项
      }
    }).$on('select', (e) => { // 暴露select事件
      window.alert(`click: ${e.idx}, params: ${JSON.stringify(e.item)}`) // 参数包含下标以及传入的菜单项
      actionPannel.closePannel() // 选择后可选关闭
    })
  },
}
```