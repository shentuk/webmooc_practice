# webmooc_practice
WebMooc《高级简历》和《餐厅游戏》项目的前端开发实战练习

需求文档详见[高级简历](https://github.com/jay007wong/webmooc-practice/blob/master/practice_chs/advancedresume.md) [餐厅游戏](https://github.com/jay007wong/webmooc-practice/blob/master/practice_chs/restaurant.md)

## 初版（initial_version）

### 要求

不使用任何框架和类库，以现有能力进行前端实践，使用HTML/CSS/原生JS完成项目开发。

### 思路

进行页面设计和CSS布局时，首先观察结构布局，在全局层面上能否划分各个模块，能否找到全局下的通用CSS布局属性和各个模块自己内部的通用布局属性。在样式布局上，提取公共类，简化类的重复性，布局方案选择浮动布局并结合flex弹性布局和grid网格布局。

在进行JS实践时，两个作业都采取的是关于直接操作DOM、事件驱动思维的方式来实现页面UI，用户互动和交互操作，其流程可以看作是：**用户输入->事件响应->执行相应的代码逻辑->更新页面状态**，

细致点说，就是首先编写静态页面（HTML与CSS样式），在特定的元素上添加事件监听，监听用户交互事件，再将事件绑定到对应的函数和处理逻辑，根据计算后的数据状态，更新相应的页面元素。代码实现思路的关注点在于触发了怎样的操作和这个操作会导致什么后果（即需要做怎样的处理），围绕着“操作”和“响应”进行。

### 心得

《高级简历》作业中，主要是针对HTML、CSS的相关知识以及一部分简单的JS基础的实践，因此，在实现过程中，逐步熟悉和掌握了结构和布局的一些技巧与要点，学会注意选择清晰、合理、富有语义化的HTML结构表达， 而不要滥用div，注意HTML的结构（架构）的合理性。

我们知道，HTML5新增许多富有语义化的标签，比如*<header>、<article>、<footer>、<article>、<aside>*等等，适当使用这些标签使得可读性大大提升，同时也能利于搜索引擎抓取识别。

CSS布局方案一定要合适准确，各种定位、浮动、flex相关知识点需要扎实到位，不仅如此，选择器的使用也要富有语义化。

《餐厅游戏》作业中，一开始针对该项目的开发思路是基于面向过程的，也就是说，编程的时候把解决问题的步骤分析出来，然后用函数把这些步骤实现，在一步一步的具体步骤中再按顺序调用函数。虽然使得编程任务明确，具体步骤可以分析清楚，但是代码重用性低，扩展能力差，后期维护难度比较大，而且这样开发效率也比较低。

于是，重新采用了面向对象的编程思想来优化代码，面向对象的本质就是定义不同的类，让类的实例工作，这样使得结构清晰，程序更加模块化和结构化，代码重用率高，易扩展和易维护，而且比较符合人类的思维方式，可以设计出低耦合的系统。

虽然核心还是事件驱动的方式，但是通过各个类的实例的状态驱动更加直观。

在不断的编程实践中，逐步感觉到编程的关键是要抽象，需要把系统需求抽象成某种高层的概念，然后在概念层次上进行编程。

### 反馈的问题

《高级简历》作业：

1.	频繁使用浮动布局，使得需要时刻注意是否造成高度塌陷而要清除浮动，没有结合其他布局方案来简化和优化布局；
  - 结合使用flex布局、网格布局等
2.	CSS选择器的层级过深，嵌套太多复杂的选择器；
  - 尽量减少嵌套层级，尽量提取公共部分
3.	sendMessage.js中DOM元素数量过多，一个一个DOM创建没有必要，并且函数体过长；
  - 减少DOM操作次数，使用模板字符串
4.	获取dom元素时使用querySelector/querySelectorAll（选择器嵌套过多）获取，性能不如通过id来获取单个元素,不如直接通过元素本身的className获取； 
5.	js代码风格没有保持一致；
   
《餐厅游戏》作业：

1.	整体代码复杂度过高，不够简洁和优雅，技术设计上比较冗余；
2.	面向对象，直接对DOM的读取和修改太多，希望的是尽量减少；

