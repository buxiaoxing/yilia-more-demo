---
title: Vue响应式原理
date: 2022-01-06 15:48:18
tags:
    - vue
    - 前端
---
**强加于他人的善意，与恶意无异**
<!--more-->

- 当你把一个普通的 JavaScript 对象传入 Vue 实例作为 data 选项，Vue 将遍历此对象所有的 property，并使用 Object.defineProperty 把这些 property 全部转为 getter/setter。Object.defineProperty 是 ES5 中一个无法 shim 的特性，这也就是 Vue 不支持 IE8 以及更低版本浏览器的原因。

- 这些 getter/setter 对用户来说是不可见的，但是在内部它们让 Vue 能够追踪依赖，在 property 被访问和修改时通知变更。这里需要注意的是不同浏览器在控制台打印数据对象时对 getter/setter 的格式化并不同，所以建议安装 vue-devtools 来获取对检查数据更加友好的用户界面。

- 每个组件实例都对应一个 watcher 实例，它会在组件渲染的过程中把“接触”过的数据 property 记录为依赖。之后当依赖项的 setter 触发时，会通知 watcher，从而使它关联的组件重新渲染。

```js
let data = {price:5, quantity:2}
let target, total, salePrice
class Dep{
    constructor(){
        this.subscribers=[]
    }
    depend(){
        if(target && !this.subscribers.includes(target)){
            this.subscribers.push(target)
        }
    }
    notify(){
        this.subscribers.forEach(sub=>sub())
    }
}
Object.keys(data).forEach(key=>{
    let internalValue = data[key]
    const dep = new Dep()
    Object.defineProperty(data, key, {
        get(){
            dep.depend()    //remember the target we're running
            return internalValue
        },
        set(newVal){
            internalValue = newVal
            dep.notify()    //run saved targets
        }
    })
})

function watcher(myFunc){
    target = myFunc
    target()
    target = null
}

watcher(()=>{
    total = data.price * data.quantity
})
watcher(()=>{
    salePrice = data.price * 0.9
})
```
 ![](https://gitee.com/buxiaoxing/image-bed/raw/master/img/20201023085214.png)


