### 浏览器

#### [浏览器跨域](https://febook.hzfe.org/awesome-interview/book1/browser-cross-origin)

- 浏览器的安全机制
- 同源策略
- JSONP
- core
- proxy
- Nginx

#### [浏览器的回流重绘](https://febook.hzfe.org/awesome-interview/book1/browser-repain-reflow)

- 解析HTML

- DOM
  
  - bytes
  
  - tag
  
  - tokens
  
  - node
  
  - dom

- CSSOM
  
  - AST
  
  - 递归

- render

- Layout

- Paint

- Composition

注意：

- CSSOM 会阻塞 JS 的执行，因为 JS 可能操作样式信息。
- CSSOM 会阻塞渲染，因为 DOM 会等待 CSSOM 生成 render 树。
- JS 会阻塞 HTML 的解析，因为 JS 可能会操作 DOM。

引起回流重绘的操作：

- 外观有变化时，会导致重绘。相关的样式属性如 color opacity 等。

- 布局结构或节点内容变化时，会导致重排。相关的样式属性如 height float position 等。

- 盒子尺寸和类型。

- 定位方案（正常流、浮动和绝对定位）。

- 文档树中元素之间的关系。

- 外部信息（如视口大小等）。

- 获取布局信息时，会导致重排。相关的方法属性如 offsetTop getComputedStyle 等。

解决方案：

- 批量操作 DOM
- 批量操作 CSS
- GPU 加速
- 布局信息缓存

#### [浏览器渲染机制](https://febook.hzfe.org/awesome-interview/book2/browser-render-mechanism)

#### [浏览器事件循环](https://febook.hzfe.org/awesome-interview/book3/browser-event-loop)

- 宏任务
- 微任务
- 函数调用栈
- 任务队列
- webAPI

#### [node事件循环](https://www.bilibili.com/video/BV13A4y1Q7N5?vd_source=d9def7d2250301f0cacc4e2d80d9fffa)

- 异步模块
- NextTick
- 微任务队列
- Timer
- Pola
- Check

#### [如何定位内存泄漏](https://febook.hzfe.org/awesome-interview/book3/browser-memory-leaks)

- 闭包
- 垃圾回收
- 引用
- 谷歌开发者工具

#### [HTTP/HTTPS](https://juejin.cn/post/6844904038509576199)

- 对称性

- 加密算法

- 非对称性

- 公钥

- 私钥

- 公证

- 数字证书

#### [前端路由实现](https://febook.hzfe.org/awesome-interview/book4/browser-router)

- SPA
  
  - Hash
    
    - 兼容性好
    
    - 锚点冲突
    
    - 不利于 SEO
    
    - hash 值不会传给服务器
  
  - History
    
    - SEO 相对 Hash 要好
    
    - 服务端可获取完整的链接和参数
    
    - 兼容差一点
    
    - 需要服务端配置

前端路由优缺点：

- 无刷新切换内容，用户体验好
- 减轻服务端压力
- 首次加载长
- SEO 不佳

#### [本地存储方式及场景](https://febook.hzfe.org/awesome-interview/book4/browser-local-storage)

- cookie
  
  - 4K
  
  - 随请求发送服务端
  
  - 可以设置失效时间

- localStorage
  
  - 5M

- sessionStorage
  
  - 5M

- IndexDB

### 工程化

#### [webpack 工作流程](https://febook.hzfe.org/awesome-interview/book1/engineer-webpack-workflow)

简易版：

- 读取配置，加载插件
- entry 开始
- 递归解析 entry 依赖的所有 module
- 找到 module.rules 对应的配置，进行编译转换，解析成一个个 chunk
- 最后将 chunk 转换成 output 输出

高级优化

- souceMap
  
  对于源代码的映射，可以更准确的进行错误提示

- hotModuleReplacement
  
  热替换

- oneOf
  
  对于 rules 中的规则之匹配一次，不再重复多余的匹配

- treeShaking
  
  抖掉无用的模块

- codeSplit
  
  将代码分割，使得真个项目不打包成一个 js 文件，也能做到按需加载

#### [Babel 原理](https://febook.hzfe.org/awesome-interview/book2/engineer-babel)

- code

- AST

- plugins

- code

### 框架

#### [Vue源码解读-初始化过程](https://juejin.cn/post/6950084496515399717#heading-11)

#### [Vue源码解读-响应式原理](https://juejin.cn/post/6950826293923414047#heading-20)

#### [Vue源码解读-异步更新](https://juejin.cn/post/6951568091893465102#heading-12)

#### [Vue源码解读-全局API](https://juejin.cn/post/6952643167715852319#heading-14)

#### [Vue源码解读-实例方法](https://juejin.cn/post/6953503236254859294)

#### [vue为什么不能检测数组的变化（索引方式）](https://juejin.cn/post/6844904046722023438)

- Object.defineProperty
  
  - 不走 walk

- JavaScript 限制？
  
  - 性能代价与用户体验收益不成正比

- Proxy

#### [vue的数据绑定机制](https://febook.hzfe.org/awesome-interview/book1/frame-vue-data-binding)

- Obsever
- Compiler
- Watcher
- Dep
- 发布订阅者模式

#### [常见框架的Diff算法](https://febook.hzfe.org/awesome-interview/book3/frame-diff#2-vue2x-diff)

- 同层级比较
  
  - text
  
  - children

- 暴力
  
  - 前后对称、交叉对比
  
  - 双指针
  
  - key
  
  - 减少DOM操作

#### [谈谈 React 和 Vue 的区别](https://febook.hzfe.org/awesome-interview/book4/frame-react-vs-vue)

- 单向数据流 与 双向数据绑定
- 数据驱动视图
- 组件化
- JSX 与 模板语法
- 拉模型 与 推模型

#### [vue2 源码总结](https://juejin.cn/post/6973196579918315533)

### 基础

#### [闭包](https://xiaozhuanlan.com/advance/3294571608)

- 特殊对象

- 函数解析时候确定

- 局部数据共享

- 变量生命周期延长

- Scope
  
  - Global 
  
  - Script
  
  - Local
  
  - Closure

- 模块化

- 柯里化

#### [闭包的作用和原理](https://febook.hzfe.org/awesome-interview/book1/js-closures)

#### [前端模块化规范](https://febook.hzfe.org/awesome-interview/book1/js-module-specs)

- ES6
- CommonJS

#### [ES5、ES6 如何实现继承](https://febook.hzfe.org/awesome-interview/book2/js-inherite)

- 原型链继承
- 构造函数继承
- 组合继承
- 寄生组合继承

#### [New 操作符的原理](https://febook.hzfe.org/awesome-interview/book2/js-new)

- 空对象
- __proto__指向构造函数的原型
- this 指向 空对象
- 返回 对象、构造函数的返回值

#### [Javascript 异步编程](https://febook.hzfe.org/awesome-interview/book3/js-async)

#### [TypeScript 中的 Interface 和 Type](https://febook.hzfe.org/awesome-interview/book3/js-ts-interface-type)

- 共同点

- 可以描述对象/函数

- 可扩展

- extends

- &

- 都可以被 class 实现

- 不同点

- type 不能重复定义，interface 可合并

- type 类型的别名，可以描述基础类型

#### [TypeScript 中的泛型](https://febook.hzfe.org/awesome-interview/book4/js-ts-generics#47-infer)

- 将类型确定的工作延迟到执行的时候，而不是定义的时候
- 扩展性

### 样式

#### [BFC](https://febook.hzfe.org/awesome-interview/book1/css-bfc)

#### [CSS 预处理器](https://febook.hzfe.org/awesome-interview/book2/css-preprocessor)

#### [移动端自适应](https://febook.hzfe.org/awesome-interview/book3/css-mobile-adaptive)

#### [水平垂直居中方案](https://febook.hzfe.org/awesome-interview/book4/css-vertical-horizontal-center)

- 文本溢出

- 计量单位

- Flex

- 盒子模型

- BFC

- 网络

### 网络安全

#### [网络安全](https://febook.hzfe.org/awesome-interview/book1/network-security)

- XSS（跨站脚本攻击）
  
  - 恶意脚本 嵌入到 URL
  
  - 恶意脚本 添加到数据库中
  
  - 内容转义

- CSRF（跨站请求伪造）
  
  - 利用 http 会带上 cookie 的特性
  
  - 采用 Token 验证

- MITM（中间人攻击）
  
  - 利用 中间人 公钥 私钥
  
  - 数据劫持

#### [HTTP 缓存机制](https://febook.hzfe.org/awesome-interview/book2/network-http-cache)

- 强制缓存
  
  - expires[expires] : MET （绝对时间戳）
  
  - cache-control[cache-control]: max-age=n （秒）

- 协商缓存
  
  - [cache-control]: no-cache （禁用强制缓存，使用协商缓存）
  
  - ETag / If-None-Match 服务器根据资源生成哈希值
  
  - Last-Modified / If-Modified-Since

- 资源的修改时间

- 节省不必要的数据传输，节省带宽

- 减少服务器负担，提高网站性能

- 降低网络延迟，加快页面的响应速度，增强用户体验

- 不恰当的缓存，可能会导致数据不能及时更新

#### [HTTP/2 和 HTTP/1.1 的对比](https://febook.hzfe.org/awesome-interview/book3/network-http-1-2)

- HTTP 1
  
  - TCP

- HTTP 1.1
  
  - 持久化连接
  
  - 管道
  
  - 队头阻塞

- HTTP 2
  
  - HTTP 流
  
  - 推送功能

- HTTP 3
  
  - UDP
  
  - QUIC
  
  - QUIC ID
  
  - 移动互联网 wifi 数据 切换

### 编码

#### [Promise](https://febook.hzfe.org/awesome-interview/book1/coding-promise)

```js
const pedding = "PEDDING";
const resolved = "RESOLVED";
const rejected = "REJECTED";

const resolvePromise = (p, res, resolve, reject) => {
  if (p === res) throw new TypeError("Chaining cycle detected for promise");
  // reject(new e("Chaining cycle detected for promise #<Promise>"));
  if (res instanceof MyPromise) res.then(resolve, reject);
  else resolve(res);
};

class MyPromise {
  constructor(executor) {
    this.state = pedding;
    this.value = undefined;
    this.resolveQueue = [];
    this.rejectQueue = [];
    try {
      executor(this.resolve.bind(this), this.reject.bind(this));
    } catch (error) {
      this.reject(error);
    }
  }

  static resolve(value) {
    if (value instanceof MyPromise) {
      return value;
    }
    return new MyPromise((resolve, reject) => {
      resolve(value);
    });
  }

  static reject(value) {
    if (value instanceof MyPromise) {
      return value;
    }
    return new MyPromise((resolve, reject) => {
      reject(value);
    });
  }

  resolve(value) {
    if (this.state == pedding) {
      this.state = resolved;
      this.value = value;
      while (this.resolveQueue.length) {
        this.resolveQueue.shift()?.(value);
      }
    }
  }
  reject(value) {
    if (this.state == pedding) {
      this.state = rejected;
      this.value = value;
      while (this.rejectQueue.length) {
        this.rejectQueue.shift()?.(value);
      }
    }
  }

  then(onResolved, onRejected) {
    onResolved =
      typeof onResolved === "function" ? onResolved : (value) => value;
    onRejected =
      typeof onRejected === "function"
        ? onRejected
        : (value) => {
            throw value;
          };

    const p = new MyPromise((resolve, reject) => {
      const onResolvedMicro = () => {
        queueMicrotask(() => {
          try {
            const res = onResolved(this.value);
            resolvePromise(p, res, resolve, reject);
          } catch (e) {
            reject(e);
          }
        });
      };
      const onRejectedMicro = () => {
        queueMicrotask(() => {
          try {
            const res = onRejected(this.value);
            resolvePromise(p, res, resolve, reject);
          } catch (e) {
            reject(e);
          }
        });
      };

      const callackMap = {
        [resolved]: onResolvedMicro,
        [rejected]: onRejectedMicro,
        [pedding]: () => {
          this.resolveQueue.push(onResolvedMicro);
          this.rejectQueue.push(onRejectedMicro);
        },
      };
      callackMap[this.state]();
    });
    return p;
  }
  catch(onRejected) {
    this.then(null, onRejected);
  }
}

MyPromise.resolve()
  .then(() => {
    console.log(0);
    return MyPromise.resolve(4);
  })
  .then((res) => {
    console.log(res);
  });

MyPromise.resolve()
  .then(() => {
    console.log(1);
  })
  .then(() => {
    console.log(2);
  })
  .then(() => {
    console.log(3);
  })
  .then(() => {
    console.log(5);
  })
  .then(() => {
    console.log(6);
  });
// MyPromise.resolve(1).then(2).then(Promise.resolve(3)).then(console.log);
```

#### [实现防抖节流函数](https://febook.hzfe.org/awesome-interview/book2/coding-throttle-debounce)

```js
let fun;
function fn() {
  console.log(123);
}
/**
 * 防抖 debounce
 */

function debounce(fn, delay = 500) {
  let timer = null;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => {
      fn.apply(null, args);
    }, delay);
  };
}

fun = debounce(fn);

fun();
fun();
fun();

/**
 * 节流 Throttled
 */
function throttled(fn, delay = 500) {
  let timer = null;
  return function (...args) {
    if (!timer) {
      timer = setTimeout(() => {
        fn.apply(this, args);
        timer = null;
      }, delay);
    }
  };
}

fun = throttled(fn, 1000);
fun();
fun();
fun();
```

#### [将列表还原为树状结构](https://febook.hzfe.org/awesome-interview/book3/coding-arr-to-tree)

```js
const isBalanced = function (root) {
  return height(root) != -1;
};

const height = function (root) {
  if (root == null) return 0;

  const l = height(root.left);
  const r = height(root.right);

  if (l == -1 || r == -1 || Math.abs(l - r) > 1) return -1;

  return ++Math.max(l, r);
};
```

### 算法

#### [平衡二叉树](https://febook.hzfe.org/awesome-interview/book1/algorithm-balanced-binary-trees)

- 后序遍历

### 综合

#### [浏览器从输入网址到页面展示的过程](https://febook.hzfe.org/awesome-interview/book1/topic-enter-url-display-xx)

- url 解析

- DNS 解析

- TCP 连接
  
  - 三次握手

- HTTP 请求

- 响应

- 渲染

- DOM

- CSSOM

- Render

- Layout

- Paint

- TCP 断开
  
  - 四次挥手

Https 在 TCP 和 HTTP 之间加了一层协议，进行加密以及认证。

#### [多图站点性能优化](https://febook.hzfe.org/awesome-interview/book2/topic-multi-pics-site-optimize)

#### [如何减少白屏的时间](https://febook.hzfe.org/awesome-interview/book3/topic-white-screen-optimization)
