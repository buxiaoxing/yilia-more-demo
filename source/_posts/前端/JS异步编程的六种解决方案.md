---
title: JS异步编程的六种解决方案
tags:
  - js
  - 异步
  - 前端
abbrlink: cf08
date: 2022-01-06 15:06:38
---
**无论你多么爱他，担心都是最差的礼物**
<!--more-->
- 回调函数

    > 将需要在异步任务后执行的操作，作为参数传入到异步操作中，当异步操作执行完成后，调用该参数执行后面的操作
    
    ```js
    ajax(url,()=>{})
    ```

    回调函数简单，容易理解和实现；但回调函数的缺点就是，容易写出回调地狱

    > 多个异步操作需要规定执行顺序时产生回调地狱
    >
    > 回调地狱导致代码不容易阅读和维护，各个部分高度耦合，使得程序结构混乱，流程那一追踪

    ````js
    ajax(url,()=>{
        //处理逻辑
        ajax(url1,()=>{
            //处理逻辑
            aja(url2,()=>{
                //处理逻辑
            })
        })
    })
    ```s

- 事件监听

  > 异步任务的执行不取决于代码的顺序，而是取决于某个事件是否发生，事件驱动

  ```js
  f1.on('done',f2)
  //f1 绑定事件 done，只有当f1发生done事件的时候才执行f2
  function f1(){
      setTimeout(function(){
          //……
          f1.trigger('done')	//触发done事件，f2立即执行
      }, 1000)
  }
  ```

  这种方式容易理解，可以绑定多个事件，每个事件可以指定多个回调函数，而且可以“去耦合”，有利于实现模块化。缺点就是整个程序都会变成事件驱动型，运行流程变得很不清晰

- 发布订阅

  > 假定存在一个"信号中心"，某个任务执行完成，就想信号中心"发布(publish)"一个信号，其他任务可以向信号中心"订阅(subscribe)"这个信号，从而知道什么时候自己可以执行。这就是发布订阅模式，又称"观察者模式"

  ```js
  jQuery.subscribe('done',f2)
  //f2 向订阅中心订阅了 done 信号
  function f1(){
      setTimeout(function(){
          //……
          jQuery.publish('done')	//执行完成后向订阅中心发布done信号
      },1000)
  }
  
  jQuery.unsubscribe('done',f2)	//f2执行完成后可以取消订阅
  ```

  > 这种方式与"事件监听类似"，但明显后者优于前者。因为可以通过查看"消息中心"，了解存在多少信号，每个信号有多少订阅者，从而监听程序的运行	

- Promise

  > ES6引入的异步编程解决方案
  
  ```mermaid
  graph LR
  a(回调函数)-- 复杂异步问题 -->b(回调地狱)
  b-->c(代码难以阅读和维护)
  c-->d(Promise)
  ```
  
  ```js
  /*##回调函数异步解决方案*/
  setTimeout(()=>{
      console.log('hello world');
      setTimeout(()=>{
          console.log('hello vueJs');
          setTimeout(()=>{
              console.log('hello Promise');   //回调函数产生的回调地狱
          },1000)
      },1000)
  }, 1000)
  /*##Promise异步解决方案*/
  new Promise((resolve, reject)=>{
      //第一次异步请求
      setTimeout(()=>{
          //成功的时候调用resolve
          resolve('hello world')   //通过resolve函数将结果返回到外部 then 处理
      }, 1000)
  }).then((data)=>{
      //处理第一次异步请求
      console.log(data);
      //第二次异步请求
      return new Promise((resolve,reject)=>{
          setTimeout(()=>{
              resolve()
          },1000)
      })
  }).then(()=>{
      //处理第二次异步请求
      console.log('hello vueJs');
      //第三次请求
      return new Promise((resolve,reject)=>{
          setTimeout(()=>{
              resolve()
          },1000)
      })
  }).then(()=>{
      //处理第三次异步请求
      console.log('hello Promise');
  })
  
  ```
  
  - Promise 怎么使用
  
    1. 将异步操作放进 Promise 中
  
    2. `new Promise(回调函数)`
  
       new -> 构造函数(1.保存一些状态信息，2.执行传入的参数(即回调函数))
  
    3. `回调函数:(resolve,reject)=>{异步操作}`
  
    4. resolve 和 reject 本身又是函数
  
    5. 通过 resolve 和 reject 将数据返回到外部 .then() .catch处理 --> 链式编程
  
       可以正确和错误的回调都在 then() 中处理
  
       ```js
       new Promise((resolve,reject)=>{
           setTimeout(()=>{
               //遇到错误调用reject，将错误返回到外部 catch 处理
               reject('hello error')
           },1000)
       }).then(data=>{
           console.log(data);
       },err=>{
           console.log(err);
       })
       ```
  
       
  
  - Promise 的三种状态
  
    `pending`: 等待状态，比如正在进行的网络请求，或定时器没有到时间
    `fulfill`: 满足状态，主动回调 resolve 时，就处于满足状态，并且回调 .then()
    `reject`: 拒绝状态，主动回调 reject 时，就处于拒绝状态，并且回调 .catch()
  
  - Promise的链式调用
  
    ```mermaid
    graph LR
    a(返回新的Promise对象)-->b(返回Promise.resolve)
    b-->c(直接返回数据)
    ```
  
    ```js
    /*最开始的链式调用*/
    new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve('hello1')
        })
    }).then((data)=>{
        console.log(data,"第一层数据处理");
        return new Promise(resolve => {
            resolve(data+'1')
        })
    }).then(data=>{
        console.log(data,'第二层数据处理');
        return new Promise(resolve => {
            resolve(data+'1')
        })
    }).then(data=>{
        console.log(data,'第三层数据处理')
    })
    
    
    /*简化new的链式调用*/
    new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve('hello1')
        })
    }).then((data)=>{
        console.log(data,"第一层数据处理");
        // return Promise.resolve(data+'1')
        return Promise.reject('error')  //抛出错误信息的简化方式
    }).then(data=>{
        console.log(data,'第二层数据处理');
        return Promise.resolve(data+'1')
    }).then(data=>{
        console.log(data,'第三层数据处理')
    }).catch(err=>{
        console.log(err);
    })
    
    
    /*最终简化版*/
    new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve('hello1')
        })
    }).then((data)=>{
        console.log(data,"第一层数据处理");
        // return data+'1'
        throw 'error'   //抛出错误的简写方式
    }).then(data=>{
        console.log(data,'第二层数据处理');
        return data+'1'
    }).then(data=>{
        console.log(data,'第三层数据处理')
    }).catch(err=>{
        console.log(err);
    })
    ```
  
  - Promise.all
  
    > 当一个任务需要多个异步任务的结果才能执行时
  
    ```js
    /*1. 通过回调函数实现*/
    let isResult1 = false
    let isResult2 = false
    $ajax({
        url: '',
        success: function () {
            console.log('结果1');
            isResult1 = true
            handleResult()
        }
    })
    $ajax({
        url: '',
        success: function () {
            console.log('结果2');
            isResult2 = true
            handleResult()
        }
    })
    function handleResult() {
        if(isResult1 && isResult2){
            //逻辑处理
        }
    }
    
    /*2. Promise的all方法，同时进行多个异步操作*/
    Promise.all([
        new Promise((resolve,reject)=>{
            $ajax({
                url: 'url1',
                success: function (data) {
                    resolve(data)
                }
            })
        }),
        new Promise((resolve,reject)=>{
            $ajax({
                url: 'url2',
                success: function (data) {
                    resolve(data)
                }
            })
        }),
    ]).then(results=>{
        results[0]  //第一个异步操作返回的结果
        results[1]  //第二个异步操作返回的结果
    })
    ```

- 生成器 Generator/yield

  > Generator与函数很像，但定义时多个 * 号，并且除了 return 以外，还可以用 yield 返回多次

  ```js
  function* foo(x){
      yield x+1
      yield x+2
      return x+3
  }
  let f = foo(3);
  f.next()    //{value: 4, done: false}
  f.next()    //{value: 5, done: false}
  f.next()    //{value: 6, done: true}
  f.next()    //{value: undefined, done: true}
  //也可以直接用循环地跌 generator 对象
  for(var x fo foo(3)){
      console.log(x)
  }
  ```

  generator 函数的特性很适合用来处理异步操作因为它的每一步yield都是按顺序的

  ```js
  function *fetch() {
      yield ajax(url, () => {})
      yield ajax(url1, () => {})
      yield ajax(url2, () => {})
  }
  let it = fetch()
  let result1 = it.next()
  let result2 = it.next()
  let result3 = it.next()
  ```

- Aysnc/Await

  > Aysnc 函数是 Generator 的优化
  >
  > Aysnc 是基于 Promise 实现的，Aysnc 返回一个 Promise 对象

  - Aysnc 对 Generator 的改进

    1. 内置执行器

       Generator 函数执行必须依靠执行器，所以才有了 co 函数库，而 aysnc 函数只带执行器。也就是说 async 函数的执行与普通函数的执行一模一样，只要一行

    2. 更广适用性

       yield 命令后面只能是 Thunk 函数或者 Promise 对象，而 async 函数的 await 命令后面，可以跟 Promise 对象和 原始类型的值（数值，字符串和布尔值，但这时等同于同步操作）

    3. 更好的语义

       async 和 await，比起 * 号和 yield ，语义更清楚了， async 表示函数里有异步操作， await 表示紧跟在后面的表达式需要等待结果

  - 缺点

    > 因为 await 将异步代码改造成了同步代码，如果多个异步代码没有依赖性却使用了 await 会导致性能的降低，代码没有依赖性的话，完全可以使用 Promise.all 的方式


