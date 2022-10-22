# TypeScipt

## 基础类型

- number

- string

- boolen

- Array\<itemType>

- Tuple -> 已知数量以及类型的数组

- enum

- any -> 慎用

- void

- null & undefined

- never

## 类型断言

as || \<itemType>

不同于 强制类型转换，这里只是绕开了 ts 的编译阶段，实际如果有问题会在，执行阶段暴露出来。

## 接口

<u>interface</u>

- readonly & const
  
  属性使用 readonly
  
  变量使用 const

- 函数类型
  `interface iFunc { (person: iPerson): iPerson; }`

- 可索引类型
  
  类似 argument 类数组类型
  
  索引分为两种类型： `number` & `string`
  
  两种索引可以同时使用，但是 number 索引的返回值必须是 string 索引返回的子类型。因为 JavaScript 解析的时候会将 number -> string 进行索引。
  
  `interfave iArray { [index: number]: number; }`

- 类类型
  
  implements
  
  多继承实现：
  
  - mixins 模拟
  
  - interface extends
  
  通过接口的多继承，实现类的多继承。

## 泛型

interface c\<T> {

  arr: Array\<T>;

}

new() 表示一个构造函数。

function create\<T>(c: { new() : T }):T {

  return new c();

}
