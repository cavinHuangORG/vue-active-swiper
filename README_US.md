# vue-active-swiper

`vue-active-swiper` is a lightweight Swiper component for Vue

![img](https://github.com/accforgit/vue-active-swiper/public/swiper-1.gif)

[简体中文](https://github.com/accforgit/vue-active-swiper/README.md) | English

## Example

- [example - basic-slot](https://github.com/accforgit/vue-active-swiper/example/basic-slot.vue)

- [example - basic-urlList](https://github.com/accforgit/vue-active-swiper/example/basic-urlList.vue)

## Install

```
npm install vue-active-swiper --save
```

## Import

### import with global

```js
// require styles
import 'vue-active-swiper/dist/VueActiveSwiper.css'

import Vue from 'vue'
import VueActiveSwiper from 'vue-active-swiper'

Vue.use(VueActiveSwiper)
```

### import with component

```js
// require styles
import 'vue-active-swiper/dist/VueActiveSwiper.css'

// in ES6 modules
import { Swiper, SwiperItem } from 'vue-active-swiper'

// in CommonJS
const { Swiper, SwiperItem } = require('vue-active-swiper')

export default {
  components: {
    Swiper,
    SwiperItem
  }
}
```

### import with script

```html
<link rel="stylesheet" href="../node-modules/vue-active-swiper/dist/VueActiveSwiper.css" charset="utf-8">
<script src="../node-modules/vue-active-swiper/dist/VueActiveSwiper.umd.min.js"></script>
```

```js
const vueSwipe = VueSwipe.Swipe
const vueSwipeItem = VueSwipe.SwipeItem

new Vue({
  el: 'body',
  components: {
    'swipe': vueSwipe,
    'swipe-item': vueSwipeItem
  }
})
```

## Usage

Work on a Vue instance:
```html
<Swiper>
  <SwiperItem>1</SwiperItem>
  <SwiperItem>2</SwiperItem>
  <SwiperItem>3</SwiperItem>
</Swiper>
```
`or`
```html
<Swiper :urlList="[
  'https://dummyimage.com/375x100/FB8A80?text=1',
  'https://dummyimage.com/375x100/29A90F?text=2',
  'https://dummyimage.com/375x100/6F9DFF?text=3'
]" />
```

## Options

### Props

|Option|Type|Description|Default|necessary|
|----|---|----|----|---|
|urlList|Array|image array <br>If specified, subcomponents(`SwiperItem`) passed in by components will not work,<br> Either `urlList` or `SwiperItem`，If both exist at the same time，`urlList` shall prevail|null|false|
|backgroundSize|String|`Specifies how the image is scaled in the sliding-container-box`(`Swiper`)，Value and Effect are the same as `CSS background-size` <br>Valid only when urlList is specified|cover|false|
|clientW|Number|Width of the sliding-container-box (`Swiper`)|`document.documentElement.clientWidth`|false|
|clientH|Number|Height of the sliding-container-box (`Swiper')|200|false|
|showCounter|Boolean|ifneed a default counter|false|false|
|counterStyle|Object|Customize the style of the default counter <br>Valid only when `showCounter` is `true`|null|false|
|startIndex|Number|Start swipe item index|0|false|
|criticalValue|Number|Proportional value of critical point <br>When it exceeds the critical point represented by this value, it will automatically slide to the next picture.|1/3|false|
|autoPlayDelay|Number|If this parameter is specified and the value `>= 0`, the value will be taken as the time of automatic rotation `delay`(`ms`) for automatic rotation;Non-designated non-automatic rotation <br>If you want to specify this value, it is generally recommended to set it to `3000`|null|false|
|duration|Number|The time(`ms`) required to automatically scroll to a stable position|350|false|
|noDragWhenSingle|Boolean|If there is only one `swipeItem`, is dragging prohibited|true|false|
|changeCallback|Function|Callback after each scroll，Callback parameter is current  `activeIndex`|-|false|

## Extra

The `Swiper`component provides a method `goto`, which allows users to specify slide to which `Swiper Item`:

```js
this.$refs.mySwiper.goto(2)
```
`goto` receives a `Number` parameter(`index`),eepresents sliding to `a Swiper Item` with `index` subscript 
`index` start at `0`

see more [example - basic-slot](https://github.com/accforgit/vue-active-swiper/example/basic-slot.vue)