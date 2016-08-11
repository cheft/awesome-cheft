# Swift3 学习笔记

__作者: `陈海峰`，本文禁止转载，违者必究__

参考教程
* [苹果官方教程](https://developer.apple.com/library/prerelease/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/Lesson1.html#//apple_ref/doc/uid/TP40015214-CH3-SW1)
* [中文教程](http://letsswift.com)
* [Swift3新特性](http://blog.csdn.net/kmyhy/article/details/51818555)

## 变量
* 用`var` 声明变量，用`let` 声明常量，常量不可更改
* 支持声明弱类型，根据值自动判断变量类型
* 支持声明强类型，比如 `var a: Double = 2`
* `？` 代表值可能为 nil（空），`!` 代表值一定不为 nil，比如：var a: String?, a?.hashValue，[详细参考](http://letsswift.com/2014/06/swift-questionmark-exclamatorymark/)
* 常用类型有 Character、String、Int、Double、Bool、Array、Dictionary、Set 等
* 字符串值必须用双引号， 比如 var str = "is String"
* 字符串拼接、加法计算都用 `+`
* 字符串拼接支持变量代入，比如 var name = 'cheft'; print("hello \(name)")
* 两种同样数据类型才可用 `+`，比如 var a = 1, var b = 2.0, 相加 Double(a) + b，其它类型转换类推
* 单行注释用 `//`，多行注释用 `/* */`
* 其它运算与其它语言类似

## [字符串](https://developer.apple.com/reference/swift/string)
* 声明 var a = "is String"; var a = "price \(2 * 6)"
* 常用属性 isEmpty、characters.count 等
* 常用方法 append、hasPrefix、hasSuffix 等

## [数组](https://developer.apple.com/reference/swift/array)
* 理论上只允许存储一种类型，声明 var a = [String](); var a = ["hello", "cheft"]; var a = Array<Int>(repeating: 1, count: 3)
* 使用 append 方法增加元素，比如 a.append("cheft")
* 使用 insert 方法在某个位置插入元素，比如 a.insert("hello", at: 0)
* 通过下标获取元素，比如 a[1]，通过 count 属性获取数组长度， 比如 a.count
* 删除某个元素 a.remove(at: 0)， 删除所有元素 a.removeAll
* 同类型数组直接用 `+` 合并， 比如 a + ["yes"]

## 字典
* 理论上只允许存储一种类型，声明 var a = ["a": "100", "b": "200"]; var b: [String: String] = [:]
* 通过 key 来访问元素，比如 a["a"]
* 也可通过属性 keys 、values 循环访问，常用属性：count

## 循环
* for 循环 for i in 1...10 {print(i)}
* 支持 var a = 0; for _ in 1..<5 { a += 1 }; print(a); `_` 下滑线在这里只是通配符
* 循环数组 var a = [1, 2, 3, 4]; for i in a {print(i)}
* 循环字典 var a = [1: 100, 2: 200, 3: 300, 4: 400]; for i in a {print(i.key); print(i.value)}
* 支持 break、continue, 比如：for i in 1...10 {if i < 5 {continue}; print(i)}; for i in 1...10 {if i > 5 {break}; print(i)}


## 控制流转
* if 、else if 、else 与其它语言一样，小括号非必要, if true {print("is true")}; if (true) {print("is true")}
* switch case 与其它语言一样，break 非必要，switch 20 {case 1: print("one"); case 10, 20: print("two"); break; case 10, 20, 30: print("three")}

## 函数
* 带参函数，定义 func hello1 (name: String) -> String { return "Hello \(name)" }; 调用 hello1(name: "Cheft!")
* 无返回值函数，定义 func hello2 (name: String, doo: String) { print("Hello \(name), I \(doo)")}; 调用 hello2(name: "Cheft!", doo: "make something")
* 多返回值函数，定义 func hello3 (name: String, doo: String) -> (a: String, b: String) {return(name, doo)};
* 省略参数 label，定义 func hello4 (_ name: String, _ doo: String) {print("Hello \(name)!, I \(doo)")}; 调用 hello4("Cheft!", "make something")

## 类
* 定义, `self` 代码自身， `init` 是构造函数，调用方式 `var p = Person(name: "Cheft")`

    ```swift
    class Person {
      var position = "深圳"
      var name = ""

      init(name: String) {
        self.name = name
      }

      func hello() {
        print("Hello \(self.name)")
      }
    }
    ```

* 继承, super 代表父亲, override 重写父类方法

   ```swift
    class Man: Person {
      var sex = "男"

      override func hello() {
        print("\(super.position) - \(self.position)")
        print("Hello \(self.name)， 我很Man")
      }
    }
    ```

## 枚举结构

* 定义数值枚举, Green、Yellow 会自增 +1

    ```swift
    enum Style: Int {
      case Blue = 3
      case Red = 6
      case Green, Yellow
    }
    ```

* 定义字符串枚举, Green、Yellow 等于自身, 使用 var s = Style(rawValue: "red"); s!.printStyle() 或者 Style.Red.printStyle()

    ```swift
    enum Style: String {
      case Blue = "blue"
      case Red = "red"
      case Green, Yellow

      func printStyle() {
        print(self.rawValue)
      }
    }
    ```

* [结构](http://www.cnblogs.com/zhidao-chen/p/3881410.html) 定义如下，结构是值类型，每个对象都是独立的，而类的对象是引用类型，结构不需要 init 方法

    ```swift
    struct Person {
      var name = ""
      var age = 18
    }
    ```

> var p = Person(); var p2 = p; p2.age = 28; 那么 p.age 还是 18，如果是类对象那么 p.age 会变成 28

## [访问协议](http://letsswift.com/2014/06/protocols/)

类似是java中的接口，用来表示哪些属性方法类型和可读可写等，可以被类、枚举、结构继承

  ```swift
  protocol PersonProtocol {
    var age : Int { get set }
    var name: String { get }
  }

  class Person: PersonProtocol {
    var age = 18
    var name = "Cheft"
  }
  ```
