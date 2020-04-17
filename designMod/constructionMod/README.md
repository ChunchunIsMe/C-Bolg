## 结构型模式
解决怎样组装现有对象，设计交互方式，从而达到实现一定的功能目的。

### 享元模式（Flyweight）
定义: 运用共享技术来减少创建对象的数量，从而减少内存占用、提供性能。
1. 享元模式提醒我们将一个对象的属性划分为内部和外部状态

    - 内部状态:可以被对象集合共享，通常不会改变
    - 外部状态:根据应用场景经常改变

2. 享元模式是利用时间换取空间的优化模式

应用场景: 只要是需要大量创建重复的类的代码块，均可以使用享元模式抽离内部/外部状态，减少重复类的创建

代码中简单实现了对象池，用来彰显设计模式的魅力
### 代理模式（Proxy）
定义: 为一个对象提供一种代理以方便对它的访问

> 代理模式可以解决避免对一些对象的直接访问，以此为基础，常见的有保护代理和虚拟代理。保护代理可以在代理中直接拒绝对对象的访问；虚拟代理可以延迟访问到真正需要的时候，以节省程序开销。

优点: 高度解耦、对象保护、易修改

缺点: 开销更大，时间更慢
### 桥接模式（Bridge）
定义: 将抽象部分具体部分实现部分分离，两者可独立变化，也可以一起工作。

> 在这种模式的实现上，需要一个对象承担桥的角色，起到连接的作用

应用场景: 封装开源库组件时，比如对外暴露一个finish函数，如果用户传入该函数，那么则会在某段代码中调用该函数，这个过程组件就起到了桥的作用，而具体的实现则是用户定义
### 装饰者模式（Decorator）
定义: 在不改变对象自身的基础上，动态的添加功能代码。

> 装饰者比继承方式更灵活，而且不污染原来的代码，代码逻辑松耦合

应用场景: 装饰者模式由于松耦合，多用于一开始不确定对象的功能、或者对象功能经常变动的时候。尤其是在参数检查、参数拦截等场景

> 注意: 桥接模式和装饰者模式代码看起来好像都是一个一个函数调用了外部的另一个函数，但是这两者还是有区别的。桥接模式是将两边的数据进行联通，而两边的数据能够通过桥梁进行沟通而又相互独立，而装饰者模式则只是将外部函数对现有函数进行装饰，并没有进行沟通
### 组合模式（Compositor）
定义: 将对象组合成树形结构以表示"部分-整体"的层次结构
    1. 用小的子对象构造成更大的父对象，而这些子对象也由更小的子对象构成
    2. 单个对象和组合对象用于用户暴露的接口具有一致性，而同种接口不同表现形式亦体现了多态性

应用场景: 组合模式可以在需要针对"树形结构"进行操作的应用中使用，例如扫描文件夹、渲染网站导航结构等等
### 适配器模式（Adapter）
定义: 为多个不兼容接口之间提供"转换器"，实现很简单，检查接口的数据，进行过滤、重组等操作，使另一接口可以使用数据即可

应用场景: 当数据不符合使用规则，就可以借助此种模式进行格式化
### 外观模式（Facade）
### 过滤器模式（Filter、Criteria）