# vue-clipper

> 图片裁剪，缩放，移动，旋转功能


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
## use
 ```
 <cp ref="clipper" :img="img" v-show="visible" :clipper-img-width="cWidth" :clipper-img-height="cWeight" @ok="ok"
                        @cancel="cancel"></cp>

 ```
```
export default {
    data() {
        return {
            visible: true,
            img: ''
        }
    },
    methods: {
        ok(data) {

        }
    }
}
```
For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
