写作意图
--------

起初，我分析underscore的源码只是想更深入的了解**函数式编程（Functional Programming）**，但分析结束后，我就觉得单纯的源码注释不足以记录我的收获、理解和感悟，所以我想把这些写下来，我粗略地将写作意图概括如下：

-	函数式编程近些年非常火爆，诸如haskwell这样的纯函数式编程语言获得了非常高的社区活跃度。js支持多范式编程，抛开underscore和lodash这样的生来为了函数编程的库不谈，诸如[redux](https://github.com/reactjs/redux)这样的库也大量运用了函数式编程，即便作为一个react+redux的业务开发者，想要深入理解的redux的实现机制，也不得不学习函数式编程。因此，学习函数式编程，将会成为js开发者的必须。

-	在阅读underscore的源码期间，被作者jashkenas（他同时也是backbone和coffee的作者）的功力深深折服，一些功能可能我也能写出，但绝对写不了如此健壮。所以，深入学习underscore源码，不仅有助于我们认识函数式编程，也能深化我们对于js中一些基础知识的理解和掌握。

-	随着backbone的衰落和lodash的崛起，underscore的热度已经不及当年，但是截止这篇文章的开始前的一个月，underscore仍然有最新的bug修复，可见作者jashkenas仍然没有放弃underscore的维护。所以现在分析underscore的源码仍然不显得过时。相较于lodash，underscore的源码更加短小，也不太涉及js中的一些奇淫巧技，所以，分析underscore更加适合js开发者的进阶。在完成了underscore的源码分析后，希望我自己有时间，也希望读者有意愿再去分析lodash的源码，后者在性能和功能上都已经超越了underscore，并且长时间霸占了npm了最热package的位置。

---

章节安排
--------

### [underscore 基础篇](base/README.md)

在基础部分，将会阐述underscore的大致结构及一些广泛用到的内部函数（internal function），这些函数被大量用到了underscore的api实现中，是我们之后理解underscore源码的必须途径。

之后，我们按照官方API文档的顺序来阐述underscore的源码实现，由于很多API的实现可以举一反三，所以，本书并不会啰嗦的阐述每个api的实现，如果真的由此需求，可以配合我写的[underscore中文注释](https://github.com/yoyoyohamapi/underscore/blob/master/underscore.analysis.js)辅助阅读。

### [underscore 集合篇](collection/README.md)

不同于数学当中的集合，在underscore中，简单地定义集合为**一个可迭代的序列**，相较于原生的ES5提供的迭代方法，underscore不仅能够对数组进行迭代，还能够对对象进行迭代。

### [underscore 数组篇](array/README.md)

这一章节我们将介绍underscore中提供的针对数组的操作，部分API已经在集合篇中有过阐述，不再赘述。

### [underscore 函数篇](function/README.md)

在js中，函数是第一型的对象，函数在js中的地位因此可见一斑。这一章节也是我认为最为重要的一章，在本章中，能够见到许多实用的针对函数的操作，以及函数式编程中的重要概念。

### [underscore 对象篇](object/README.md)

本章中，将介绍underscore中操作对象的api。

### [underscore 实用工具篇](utility/README.md)

underscore还提供了不少工具函数，来提供一些周边功能，如字符逃逸等。但其中最重要的是其提供的模板引擎工具，我将会花费很大笔墨对其进行描述

### [underscore 内容拾遗](supply/README.md)

最后，在收尾阶段，我们还会介绍underscore提供的面向对象风格（OOP Style），链式调用（Chain）等内容。

---

感谢
----

本文基于underscore的[1.8.3版本](https://github.com/jashkenas/underscore/tree/1.8.3)进行分析, 在阅读官方文档时遇到的困难时，特别感谢[underscore中文教程](http://www.css88.com/doc/underscore/)提供的帮助。

> 欢迎转载或者引用，但请注明出处，这算是对我工作成果的认可和尊重。也欢迎拍砖，相应问题可以发到[discussion](https://www.gitbook.com/book/yoyoyohamapi/undersercore-analysis/discussions)，我会最快时间进行更正或者解答。
