模板引擎是数据变为试图的最优雅的方法

### 数据变为视图方法：

- 纯DOM：`document.creatElement() element.appendChild()`
- 数组 join
- ES6 反引号
- Mustache

### Mustache 库基本使用

`https://cdn.staticfile.org/mustache.js/4.2.0/mustache.js`

- `Mustache.render(templateStr, data);`
  
  - 遍历对象数组
    
    ```javascript
    import Mustache from 'mustache';
    
    let templateStr = `
        <div>
          {{#arr}}
            <h1>{{name}}</h1>
        {{/arr}}
      </div>
    `;
    
    let data = {
      arr: [
        {name: 'a'},
        {name: 'b'},
      ]
    };
    
    let domStr = Mustache.render (templateStr,data);
    console.log(domStr)
    ```
    
    ![JTHlO.png](https://s1.328888.xyz/2022/03/29/JTHlO.png)
  
  - 遍历普通数组
    
    ```javascript
    import Mustache from 'mustache';
    
    let templateStr = `
        <div>
          {{#arr}}
            <h1>{{.}}</h1>
        {{/arr}}
      </div>
    `;
    
    let data = {
      arr: [
        'a','b'
      ]
    };
    
    let domStr = Mustache.render (templateStr,data);
    console.log(domStr)
    ```
  
  - 布尔值
    
    ```javascript
    import Mustache from 'mustache';
    
    let templateStr = `
        <div>
          {{#m}}
            <h1>你好</h1>
        {{/m}}
      </div>
    `;
    
    let data = {
      m: false,
    };
    
    let domStr = Mustache.render (templateStr,data);
    console.log(domStr)
    ```

### 正则模拟模板数据填充

最简单的数据填充，无法遍历

正则中（）括起来的，会被捕获通过 `$1` 获取，多个则 `$n`

Mustache 底层原理并不是通过正则

```javascript
let templateStr = '<h1>我是{{name}},今年{{age}}岁</h1>'; 
let data = {
  name: '梨花',
  age: '18',
};

function render(templateStr,data){
    return templateStr.replace(/\{\{(\w+)\}\}/g,function(findStr, $1){
    console.log(findStr,$1)
    return data[$1];
  });
}

render(templateStr,data);
```

![JT2fg.png](https://s1.328888.xyz/2022/03/29/JT2fg.png)

### Mustache 底层原理

![JTDPP.png](https://s1.328888.xyz/2022/03/29/JTDPP.png)

tokens：JS 嵌套数组，模板字符串的 JS 形式 （抽象语法树、虚拟节点）

简单模板

```javascript
/*
模板字符串 let templateStr = '<h1>我是{{name}},今年{{age}}岁</h1>'; 
tokens [
  ["text","<h1>我是"],
  ["name","name"],
  ["text",",今年"],
  ["name","age"],
  ["text","岁</h1>"]
]
*/
```

带有循环模板

```javascript
/*
模板字符串 
let templateStr = `
    <div>
      {{#arr}}
        <h1>{{.}}</h1>
    {{/arr}}
  </div>
`; 
tokens [
  ["text", "<div>"],
  ["#", "arr", [
    ["text", "<h1>"]
    ["name", "."]
    ["text", "</h1>"]
  ]]
  ["text", "</div>"],
]
多层循环 tokens会更深
*/
```

### 开始手写Mustache